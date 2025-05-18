---
tags:
- design-pattern-software-architecture
- oop-patterns-gof
- 게임개발-면접-설계-유지보수
aliases:
- DesignPattern
- 디자인패턴

## 디자인 패턴 (Design Pattern)

#### What is Design Pattern

- 정의 (Definition):
    - 디자인 패턴은 소프트웨어 설계에서 반복적으로 등장하는 문제를 효율적으로 해결하기 위한 **일반화된 설계 해법**입니다.
    - 객체지향 프로그래밍(OOP)에서 코드의 재사용성, 확장성, 유지보수성을 높이기 위해 사용됩니다.
    - 대표적으로 GoF(Gang of Four) 23가지 패턴이 널리 알려져 있습니다.

- 예시 (Examples):
    - 싱글톤(Singleton): 전역에서 하나의 인스턴스만 존재하도록 보장
    - 옵저버(Observer): 상태 변화 시 여러 객체에 알림
    - 팩토리(Factory): 객체 생성 로직을 분리
    - 코드 예시 (C# Singleton):
```csharp
public class GameManager {
    private static GameManager instance;
    public static GameManager Instance => instance ??= new GameManager();
    private GameManager() { }
}
```
    - 코드 예시 (C# Observer):
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
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://en.wikipedia.org/wiki/Design_Patterns)
    - GoF 23 패턴(생성, 구조, 행위) 분류 및 사례
- [Refactoring Guru: Design Patterns](https://refactoring.guru/design-patterns)
    - 각 패턴의 구조, 장단점, 코드 예시, 실전 적용법

## 주제별 세부 내용 정리와 설명
- **패턴 분류**:
    - 생성(Creational): Singleton, Factory, Builder, Prototype, Abstract Factory
    - 구조(Structural): Adapter, Bridge, Composite, Decorator, Facade, Proxy, Flyweight
    - 행위(Behavioral): Observer, Command, Strategy, State, Template Method, Iterator, Mediator, Visitor, Chain of Responsibility, Memento, Interpreter
- **GoF 23 패턴**: 객체지향 설계의 표준 해법, 다양한 언어/플랫폼에서 활용
- **장점**: 코드 재사용, 설계 표준화, 유지보수/확장성 향상, 협업 용이
- **단점/주의점**: 남용 시 복잡도 증가, 과설계(Overengineering) 위험
- **실전 팁**: 패턴은 문제/상황에 맞게 선택, 불필요한 패턴 적용은 피할 것
- **Unity/게임 개발**: 싱글톤(매니저), 옵저버(이벤트), 오브젝트 풀링(최적화) 등 자주 활용

## Unity/게임 개발에서의 활용
- 싱글톤: GameManager, AudioManager 등 전역 관리
- 옵저버: 이벤트 시스템, UI 갱신, 상태 변화 알림
- 오브젝트 풀링: 총알/이펙트 등 반복 생성/파괴 최적화
- 상태(State), 전략(Strategy): AI, 행동 전환, 입력 처리 등

## 예상 면접 질문과 답변
- Q. 디자인 패턴이란?
  A. 반복되는 설계 문제를 해결하는 일반화된 해법(설계 템플릿)입니다.
- Q. GoF 23 패턴의 분류는?
  A. 생성, 구조, 행위 패턴으로 나뉩니다.
- Q. 싱글톤 패턴의 장단점은?
  A. 전역 인스턴스 보장(장점), 테스트/확장 어려움(단점).
- Q. 옵저버 패턴의 활용 예시는?
  A. 이벤트 시스템, UI 갱신, 상태 변화 알림 등.
- Q. 오브젝트 풀링이 필요한 이유는?
  A. 반복 생성/파괴 비용 절감, 성능 최적화.
- Q. 패턴 남용의 문제점은?
  A. 코드 복잡도 증가, 과설계 위험.

## 관련 개념 (Related Concepts)
- [[OOP (객체지향 프로그래밍)]] #oop #design #architecture
- [[SOLID 원칙]] #solid #design #pattern
- [[Refactoring]] #refactoring #design
- [[Unity 패턴 활용]] #unity #pattern #game 