

## 싱글톤 패턴 (Singleton Pattern)

#### What is Singleton Pattern

- 정의 (Definition):
    - 싱글톤은 **프로그램 전체에서 단 하나의 인스턴스**만 존재하도록 보장하는 생성(Creational) 디자인 패턴입니다.
    - 전역 상태, 리소스 관리, 매니저 등에 활용됩니다.

- 예시 (Examples):
    - 게임의 GameManager, AudioManager 등 전역 관리 객체
    - 코드 예시 (C#):
```csharp
public class GameManager {
    private static GameManager instance;
    public static GameManager Instance => instance ??= new GameManager();
    private GameManager() { }
}
```

## Literature Review

#### Gamma et al., 1994
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://en.wikipedia.org/wiki/Singleton_pattern)
    - 싱글톤의 구조, 장단점, 활용 사례

## 주제별 세부 내용 정리와 설명
- **구조**: 생성자를 private으로 제한, static 인스턴스 제공
- **장점**: 전역 인스턴스 보장, 리소스 공유, 접근 용이
- **단점**: 테스트/확장 어려움, 의존성 증가, 멀티스레드 환경 주의
- **Unity/게임 개발**: GameManager, AudioManager, InputManager 등에서 자주 사용
- **실전 팁**: 필요 이상 남용 금지, DI/테스트 고려, 멀티스레드 안전성 필요시 lock 등 추가

## 예상 면접 질문과 답변
- Q. 싱글톤 패턴이란?
  A. 프로그램 전체에서 단 하나의 인스턴스만 존재하도록 보장하는 패턴입니다.
- Q. 싱글톤의 장단점은?
  A. 전역 인스턴스 보장(장점), 테스트/확장 어려움(단점).
- Q. Unity에서 싱글톤 활용 예시는?
  A. GameManager, AudioManager 등 전역 관리 객체.
- Q. 멀티스레드 환경에서 싱글톤 안전하게 구현하려면?
  A. lock, double-check locking 등 동기화 필요.

