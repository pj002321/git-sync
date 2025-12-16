Model, View, Controller로 분리해서 데이터, 화면, 제어 로직의 책임을 명확히 나누는 아키텍처 패턴.

왜 쓰는지?
- 전투 로직(Model), UI(View), 입력 및 상태 제어(Controller)를 분리하기 위해 활용

언제 쓰는지?
- UI 변경 가능성이 높고, 데이터 로직이 복잡할 때

장점
- 역할이 명확해 코드 가독성과 유지보수성이 높다.
- Model 단위 테스트가 쉽다.

단점
- Controller가 비대해질 위험이 있다.
- 초기 설계 비용이 든다.

구조
```csharp

// MODEL
public class PlayerModel
{
    public int HP { get; private set; } = 100;

    public void Damage(int value)
    {
        HP -= value;
    }
}

// VIEW
public class PlayerView
{
    public void UpdateHP(int hp)
    {
        Console.WriteLine($"HP: {hp}");
    }
}

// CONTROLL
public class PlayerController
{
    private PlayerModel model;
    private PlayerView view;

    public PlayerController(PlayerModel m, PlayerView v)
    {
        model = m;
        view = v;
    }

    public void Hit(int damage)
    {
        model.Damage(damage);
        view.UpdateHP(model.HP);
    }
}


User Input
   ↓
Controller
   ↓
Model (데이터 변경)
   ↓
View (화면 갱신)


```

Unity는 전통적인 MVC 구조와 잘 맞지 않는다.
-> **View + Controller가 MonoBehaviour에 합쳐져 있음**

### 1. View가 순수하지 않음
- Unity View는 `MonoBehaviour` + `GameObject`
- UI 이벤트, 애니메이션, 입력이 같이 들어감
### 2. Controller가 엔진에 종속
- `Update`, `OnClick`을 엔진이 호출
- 독립적인 Controller 객체 구성 어려움
### 3. 생명주기 제어 불가
- 생성/파괴 시점이 Unity 엔진에 종속됨

[[DesignPattern]]