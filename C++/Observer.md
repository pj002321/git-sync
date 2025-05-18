

## 옵저버 패턴 (Observer Pattern)

#### What is Observer Pattern

- 정의 (Definition):
    - 옵저버는 **한 객체의 상태 변화**를 여러 객체(옵저버)에게 자동으로 알리는 행위(Behavioral) 디자인 패턴입니다.
    - 이벤트 시스템, UI 갱신, 상태 변화 알림 등에 활용됩니다.

- 예시 (Examples):
    - 게임 엔진의 이벤트 시스템, UI 자동 갱신
    - 코드 예시 (C++):
```cpp
class IObserver {
public:
    virtual void OnNotify() = 0;
    virtual ~IObserver() = default;
};
class Subject {
    std::vector<IObserver*> observers;
public:
    void Add(IObserver* obs) { observers.push_back(obs); }
    void Notify() { for(auto* o : observers) o->OnNotify(); }
};
```

## 주제별 세부 내용 정리와 설명
- **구조**: Subject(관찰 대상)와 Observer(관찰자)로 분리, 상태 변화 시 알림
- **Modern C++**: 스마트 포인터로 메모리 관리, 람다/함수 객체 활용 가능
- **장점**: 느슨한 결합, 확장성, 자동화된 알림
- **단점**: 복잡도 증가, 순환 참조/메모리 누수 주의
- **게임/엔진 활용**: 이벤트 시스템, UI, 상태 변화 알림 등에서 자주 사용
- **실전 팁**: 스마트 포인터/RAII로 메모리 관리, 구독 해제(메모리 누수 방지) 주의

## 예상 면접 질문과 답변
- Q. 옵저버 패턴이란?
  A. 한 객체의 상태 변화가 여러 객체에 자동으로 알림되는 패턴입니다.
- Q. Modern C++에서 옵저버 패턴 구현 시 주의점은?
  A. 스마트 포인터/RAII로 메모리 관리, 순환 참조 방지.

[[C++]]  