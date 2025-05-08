---
tags:
- C++
- DesignPatterns
- Singleton
- OOP
- Architecture
aliases:
- Singleton
- CppSingleton
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 싱글톤 (Singleton)

#### What is Singleton

- 정의 (Definition):
	- 싱글톤은 클래스의 인스턴스가 하나만 존재하도록 보장하는 디자인 패턴입니다. (Gamma et al., 1994)
	- 전역 접근점을 제공하면서도 인스턴스의 수를 제한합니다.

- 예시 (Examples):
	- 기본 싱글톤: `static Singleton& getInstance()`
	- 스레드 안전 싱글톤: `std::call_once` 사용
	- 마이어스 싱글톤: `static Singleton& getInstance() { static Singleton instance; return instance; }`
	- 의존성 주입 싱글톤: `static void setInstance(std::unique_ptr<Singleton> instance)`
	- CRTP 싱글톤: `template<typename T> class Singleton<T>`

## Literature Review

#### Gamma et al., 1994
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 싱글톤은 전역 상태를 캡슐화합니다.
	- 스레드 안전성에 주의해야 합니다.
	- 테스트와 모듈성에 영향을 줄 수 있습니다.

## 관련 개념 (Related Concepts)

- [[Thread Safety (스레드 안전성)]] #cpp #threading #safety
	- 멀티스레드 환경에서의 안전한 싱글톤 구현

- [[Dependency Injection (의존성 주입)]] #cpp #design #patterns
	- 싱글톤의 대안으로 사용되는 패턴

- [[RAII (Resource Acquisition Is Initialization)]] #cpp #raii #resource
	- 싱글톤의 리소스 관리 방법 