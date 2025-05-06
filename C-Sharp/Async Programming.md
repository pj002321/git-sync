## Async Programming

>[!COROUTINE]
>Unity의 프레임 간 시간 지연 또는 비동기 흐름 제어를 쉽게 구현할 수 있도록 해주는 C# 함수.
>IEnumerator 타입을 반환하고, StartCoroutine으로 실행
>yield return 구문으로 일시정지와 재개 구현 가능.

## ✅ 주요 `yield return` 타입들

|구문|설명|
|---|---|
|`yield return null`|다음 프레임까지 대기|
|`yield return new WaitForSeconds(3f)`|3초 대기|
|`yield return new WaitUntil(() => 조건)`|조건이 참이 될 때까지 대기|
|`yield return new WaitForEndOfFrame()`|해당 프레임 렌더링이 끝날 때까지 대기|
|`yield return new WaitForFixedUpdate()`|다음 FixedUpdate()까지 대기|
## ✅ Coroutine 정지 / 관리
```
`Coroutine handle;  
void Start() {
handle = StartCoroutine(DoSomething()); 
}  
void StopMyCoroutine() {
if (handle != null) StopCoroutine(handle);
}`

```

- `StopCoroutine(코루틴 이름)` 혹은 `StopAllCoroutines()` 가능
    
- `OnDisable()` 시 자동 정지됨

## ✅ Coroutine vs Update 차이

|항목|Coroutine|Update|
|---|---|---|
|주 목적|비동기 흐름 제어 (시간 지연 등)|매 프레임 로직 처리|
|호출 주기|필요 시 수동 호출|프레임마다 자동 호출|
|일시정지|가능 (`yield return`)|불가능|
|처리 방식|`IEnumerator` 기반 흐름|일반 메서드 로직|
## ✅ Coroutine vs async/await: 총정리 비교표

|항목|Coroutine|async/await|
|---|---|---|
|실행 환경|Unity 전용|C# (.NET) 표준|
|주 쓰임|프레임 간 시간 지연, 애니메이션, 순차적 동작|네트워크, 파일 IO, 병렬 계산 등|
|일시정지 방식|`yield return` (프레임 단위)|`await` (비동기 Task 완료까지)|
|쓰레드 처리|**메인 스레드**에서 실행|기본적으로 **비동기 스레드** 사용 가능|
|사용 가능 조건|`MonoBehaviour` 상속 필수 + Unity 환경|C# 5.0 이상 (Unity 2017.1+), Task 지원|
|장점|Unity의 **프레임 기반 흐름 제어에 최적화**|복잡한 IO나 비동기 작업을 **간결하게 처리**|
|단점|병렬처리 불가, 에러 추적 어려움|Unity 엔진 API 접근은 메인 스레드에서만 가능|

## ✅ UniTask

Unity에서 `async/await`를 사용할 때 생기는 **퍼포먼스 문제**와 **불편함**을 해결하기 위해 나온 경량 비동기 라이브러리.  

| https://github.com/Cysharp/UniTask.git?path=src/UniTask/Assets/Plugins/UniTask
| using Cysharp.Threading.Tasks;
## UniTask가 필요한 이유

| 문제                                                                                      | UniTask 해결 방식                                                        |
| --------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Unity는 `async/await`가 기본적으로 `Task`를 사용하지만, `Task`는 **GC (Garbage Collection)** 오버헤드가 있음 | `Task` 대신 **GC-free한 `UniTask`** 사용                                  |
| `await Task.Yield()`는 성능 저하 + 불안정                                                       | `await UniTask.Yield()`는 성능 최적화됨                                     |
| Unity API를 사용하는 코드를 `await`하려면 `IEnumerator`와 혼용 불편                                     | **코루틴 스타일**의 흐름을 유지한 채 `await` 사용 가능                                 |
| `CancellationToken`, 시간 지연, 조건 대기 등 다양하게 `await` 불가                                     | `UniTask.Delay`, `WaitUntil`, `WaitForSeconds` 등 Unity에 특화된 await 지원 |
## ✅ Coroutine과의 비교 요약

| 항목           | Coroutine             | UniTask                  |
| ------------ | --------------------- | ------------------------ |
| 가독성          | 구조적 흐름에 유리            | 직관적 `await` 문법           |
| 퍼포먼스         | 프레임 기반으로 자연스러움        | 최적화된 `await` 흐름, GC-free |
| 병렬 처리        | X                     | O                        |
| Unity API 접근 | O                     | O (단, 메인 스레드에서만)         |
| 취소 제어        | 어렵다 (`StopCoroutine`) | `CancellationToken` 지원   |
| 디버깅          | 어려움                   | `try/catch`로 예외 처리 용이    |

- yield return new WaitForSeconds / yield return new WaitForSecondsRealtime  
    == await UniTask.Delay
- yield return null == await UniTask.Yield / await UniTask.NextFrame
- yield return WaitForEndOfFrame == await UniTask.WaitForEndOfFrame
- yield return new WaitForFixedUpdate // await UniTask.WaitForFixedUpdate
- yield return WaitUntil == await UniTask.WaitUntil

## 💬 Coroutine은 언제 사용?
시간이 흐른 후에 실행하거나, 여러 프레임에 걸쳐서 천천히 작업할 때 사용.
예를 들어 UI 애니메이션, 로딩 효과, 순차적 이벤트 처리 등에 적합.

## 💬 Coroutine 과 async/await 차이는 뭔가요?
Coroutine은 Unity 엔진에 특화된 프레임 기반 비동기 처리이며, 메인 쓰레드에서 실행된다.
반면, async/await는 .NET 기반의 쓰레드 기반 비동기 처리로, 멀티쓰레드 작업에 더 적합하지만 Unity에서는 제한적이다. (UniTask)


[[C-Sharp&Unity]]
