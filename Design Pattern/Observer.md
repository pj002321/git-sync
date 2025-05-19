

## 옵저버 패턴 (Observer Pattern)

#### What is Observer Pattern

- 정의 (Definition):
    - 옵저버는 **한 객체의 상태 변화**를 여러 객체(옵저버)에게 자동으로 알리는 행위(Behavioral) 디자인 패턴입니다.
    - 이벤트 시스템, UI 갱신, 상태 변화 알림 등에 활용됩니다.

- 예시 (Examples):
    - 게임의 이벤트 시스템, UI 자동 갱신
    - 코드 예시 (C#):
```csharp
public interface IObserver { void OnNotify(); }
public class Subject {
    private List<IObserver> observers = new();
    public void Add(IObserver obs) => observers.Add(obs);
    public void Notify() { foreach(var o in observers) o.OnNotify(); }
}
```

## Literature Review

#### Gamma et al., 1994
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://en.wikipedia.org/wiki/Observer_pattern)
    - 옵저버의 구조, 장단점, 활용 사례

## 주제별 세부 내용 정리와 설명
- **구조**: Subject(관찰 대상)와 Observer(관찰자)로 분리, 상태 변화 시 알림
- **장점**: 느슨한 결합, 확장성, 자동화된 알림
- **단점**: 복잡도 증가, 순환 참조/메모리 누수 주의
- **Unity/게임 개발**: 이벤트 시스템, UI, 상태 변화 알림 등에서 자주 사용
- **실전 팁**: 이벤트/델리게이트 활용, 구독 해제(메모리 누수 방지) 주의

## 예상 면접 질문과 답변
- Q. 옵저버 패턴이란?
  A. 한 객체의 상태 변화가 여러 객체에 자동으로 알림되는 패턴입니다.
- Q. 옵저버의 장단점은?
  A. 느슨한 결합/확장성(장점), 복잡도/메모리 누수(단점).
- Q. Unity에서 옵저버 활용 예시는?
  A. 이벤트 시스템, UI 자동 갱신 등.
- Q. 옵저버 패턴에서 메모리 누수 방지법은?
  A. 구독 해제(이벤트 핸들러 제거) 필요.

[[DesignPattern]]