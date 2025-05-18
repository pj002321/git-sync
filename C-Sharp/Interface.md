---
tags:
-인터페이스-계약-다형성-구현-추상화
-interface-contract-polymorphism-implementation-abstraction
-게임개발-면접-설계-유지보수
aliases:
-인터페이스
-Interface
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 인터페이스 (INTERFACE)

#### What is Interface

- 정의 (Definition):
	- 인터페이스는 클래스나 구조체가 구현해야 하는 멤버(메서드, 속성 등)의 집합을 정의하는 추상 타입이다 (Hejlsberg et al., 2003).
	- 다형성과 느슨한 결합을 지원하여, 코드의 유연성과 확장성을 높인다 (Hejlsberg et al., 2003).
	- 게임 개발에서 다양한 오브젝트의 공통 동작 정의에 활용된다 (Unity Technologies, 2020).
- 예시 (Examples):
	- IAttackable 인터페이스를 구현하여 다양한 적 캐릭터에 공격 기능 부여 (Hejlsberg et al., 2003).
	- Unity에서 MonoBehaviour 인터페이스를 상속받아 게임 오브젝트 동작 구현 (Unity Technologies, 2020).

## Literature Review

#### Hejlsberg et al., 2003
- [The C# Programming Language](https://doi.org/10.5555/861282)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- 인터페이스의 정의와 사용법
	- 다형성 및 느슨한 결합 구현
	- 코드 유연성 향상

#### Unity Technologies, 2020
- [Unity Scripting API](https://docs.unity3d.com/ScriptReference/MonoBehaviour.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 인터페이스 활용
	- MonoBehaviour와 인터페이스의 차이
	- 게임 오브젝트 관리

## 관련 개념 (Related Concepts)

- [[다형성 (POLYMORPHISM)]] #interface-polymorphism
	- 동일한 인터페이스로 다양한 동작을 구현하는 개념
- [[추상화 (ABSTRACTION)]] #interface-abstraction
	- 불필요한 세부 구현을 숨기고, 필요한 기능만 노출하는 개념
- [[구현 (IMPLEMENTATION)]] #interface-implementation
	- 인터페이스에 정의된 멤버를 실제로 작성하는 과정 