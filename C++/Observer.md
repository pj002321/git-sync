---
tags:
- C++
- DesignPatterns
- Observer
- OOP
- Architecture
aliases:
- Observer
- CppObserver
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 옵저버 (Observer)

#### What is Observer

- 정의 (Definition):
	- 옵저버는 객체 간의 일대다 의존성을 정의하는 디자인 패턴입니다. (Gamma et al., 1994)
	- 한 객체의 상태가 변경되면 그 객체에 의존하는 모든 객체들이 자동으로 통지받고 업데이트됩니다.

- 예시 (Examples):
	- 기본 옵저버: `virtual void update() = 0`
	- 이벤트 기반 옵저버: `std::function<void()> callback`
	- 스레드 안전 옵저버: `std::mutex` 사용
	- 약한 참조 옵저버: `std::weak_ptr<Observer>`
	- 구독/발행 모델: `void subscribe(Observer* obs)`, `void notify()`

## Literature Review

#### Gamma et al., 1994
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 옵저버는 느슨한 결합을 촉진합니다.
	- 발행-구독 패턴의 기반이 됩니다.
	- 메모리 누수에 주의해야 합니다.

## 관련 개념 (Related Concepts)

- [[Publish-Subscribe (발행-구독)]] #cpp #design #patterns
	- 옵저버 패턴의 확장된 형태

- [[Event Handling (이벤트 처리)]] #cpp #design #patterns
	- 옵저버 패턴의 일반적인 사용 사례

- [[Smart Pointers (스마트 포인터)]] #cpp #memory #management
	- 옵저버의 수명 관리에 사용되는 도구 