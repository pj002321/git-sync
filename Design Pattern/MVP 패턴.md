View와 Model을 완전히 분리하고, 모든 제어 로직을 Presenter(중재자)가 담당하는 UI 중심 아키텍처 패턴.
View는 수동적이고, 중재자가 Model 과 View 사이를 전부 중재한다.

왜 쓰는지?
- UI로직을 View에서 제거해, 테스트 가능성과 유지보수성을 높이기 위해 사용.

언제 쓰는지?
-  UI 로직이 복잡할 때 View가 판단하지 않을 때 (로그인, 상점, 인벤토리 etc)

장점
- VIew와 Model의 완전한 분리, 단위 테스트 가능

단점
- Present가 비대해질 수 있으며, 클래스 수 증가, 과설계 주의

구조
```csharp

// MODEL
public class PlayerModel
{
    public int HP { get; private set; } = 100;
    public void Damage(int value) => HP -= value;
}


// VIEW
public interface IPlayerView
{
    void UpdateHP(int hp);
}


// Presenter
public class PlayerPresenter
{
    private IPlayerView view;
    private PlayerModel model;

    public PlayerPresenter(IPlayerView v, PlayerModel m)
    {
        view = v;
        model = m;
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

Model → 순수 C# 클래스
View → MonoBehaviour (UI, 화면)
Controller → MonoBehaviour or Service

[[DesignPattern]]