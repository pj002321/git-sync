# Life Cycle

>[!LIFE CYCLE]
>MonoBehaviour를 기반으로 동작하는 Unity 스크립트의 실행 흐름을 의미합니다. 엔진이 오브젝트를 **로드, 활성화, 업데이트, 비활성화, 파괴**하는 일련의 흐름에 따라 특정 콜백 함수들이 호출


## ✅ Unity Life Cycle 구조 (전체 흐름)

### 1. **초기화 단계**

|함수|설명|
|---|---|
|`Awake()`|가장 먼저 호출됨. 다른 스크립트 참조 준비. 비활성 오브젝트에서도 실행됨.|
|`OnEnable()`|오브젝트가 활성화될 때 호출됨. 매니저 등록 등 초기화에 자주 사용.|
|`Start()`|모든 Awake 이후에 호출됨. 활성화된 경우에만 실행됨. 오브젝트 참조 안전.|

---

### 2. **프레임 업데이트 단계**

|함수|설명|
|---|---|
|`Update()`|매 프레임마다 호출. 입력 처리, 일반 로직 처리.|
|`LateUpdate()`|모든 Update 후에 호출. 카메라 따라가기 등에 사용.|
|`FixedUpdate()`|일정한 시간 간격으로 호출. 물리 계산에 사용. (Time.fixedDeltaTime)|

---

### 3. **렌더링 직전**

|함수|설명|
|---|---|
|`OnWillRenderObject()`|해당 오브젝트가 카메라에 보일 때 호출|
|`OnBecameVisible()` / `OnBecameInvisible()`|카메라 프러스텀 안팎 진입 시|

---

### 4. **비활성화 및 종료 단계**

|함수|설명|
|---|---|
|`OnDisable()`|비활성화 시 호출됨. OnEnable과 짝을 이룸|
|`OnDestroy()`|오브젝트가 파괴될 때 호출됨|
## ⚠ `Start()`에서 다른 오브젝트 접근 시 NullReferenceException

- A 오브젝트의 `Start()`에서 B 오브젝트를 `Find()`하거나 참조하려고 할 때, B 오브젝트가 아직 `Awake()` 상태일 수 있음.
    
- 특히 **실행 순서가 보장되지 않는 경우** 문제 발생.
```
void Start() {
    GameObject obj = GameObject.Find("Player");
    obj.GetComponent<PlayerController>().Initialize(); // Null 발생 가능
}

```
참조가 필수라면 `Awake()`에서 미리 찾아서 캐싱하거나, `Script Execution Order`를 활용해 명시적으로 순서 조정.

## ⚠ `OnDisable()`에서 코루틴을 중단하지 않음

비활성화된 오브젝트에서 코루틴이 계속 돌고 있으면, 의도치 않게 로직이 수행됨.
```
void OnEnable() {
    StartCoroutine(SomeCoroutine());
}

void OnDisable() {
    // 코루틴 정지 안 함
}

-------------------------------------------------

Coroutine routine;

void OnEnable() {
    routine = StartCoroutine(SomeCoroutine());
}

void OnDisable() {
    if (routine != null) StopCoroutine(routine);
}

```

## ⚠ FixedUpdate() 입력 처리

`Input.GetKey()`를 `FixedUpdate()`에서 처리하면, 프레임 수보다 물리 업데이트가 적거나 많을 경우 입력이 씹힘.
```
void FixedUpdate() {
    if (Input.GetKey(KeyCode.Space)) {
        // 점프 처리
    }
}
--------------------------------------------------
bool jumpRequested = false;

void Update() {
    if (Input.GetKeyDown(KeyCode.Space)) {
        jumpRequested = true;
    }
}

void FixedUpdate() {
    if (jumpRequested) {
        // 점프 처리
        jumpRequested = false;
    }
}


```

## ⚠`OnDestroy()`에서 참조된 싱글톤에 접근

```
void OnDestroy() {
    GameManager.Instance.DoSomething(); // NullReference 가능
}

```
- 앱 종료나 씬 언로드 중에 싱글톤이 먼저 Destroy되면, 그 이후 오브젝트에서 접근할 경우 예외 발생
- `Application.isPlaying`이나 `GameManager.Instance != null` 체크 후 접근.


---


## 💬 Awake()와 Start()의 차이는 무엇인가요?
Awake() 는 오브젝트가 생성되자마자 호출, 오브젝트가 비활성화 상태라도 실행.
Start() 는 오브젝트가 활성화 상태일 때만 실행되며, Awake() 이후 한 번만 호출된다.

## 💬 Update() 와 FixedUpdate() 의 차이점
Update는 프레임마다 호출되고 주로 입력 처리나 로직 처리에 사용한다.
FixedUpdate는 물리 연산 전용이며 일정한 시간 간격으로 호출되어 Rigidbody, Force 관련 로직을 사용할 때 쓰인다.

## 💬 OnEnable과 Start 중 초기화 배치관련
OnEnable 은 매번 활성화 시 호출되기 때문에 반복되는 초기화에 적합하고, Start는 처음 한 번만 호출되므로 1회성 초기화에 적합하다.

`Application.quitting` 시점의 종료 처리 주의 (`OnDestroy`보다 먼저 관리해야 함)

[[Unity]]
