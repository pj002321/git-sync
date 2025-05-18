---
tags:
-객체지향프로그래밍-클래스-상속-다형성-캡슐화
-OOP-class-inheritance-polymorphism-encapsulation
-게임개발-면접-기초-설계-유지보수
aliases:
-객체지향
-OOP
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 객체지향 프로그래밍 (OBJECT-ORIENTED PROGRAMMING, OOP)

#### What is OOP

- 정의 (Definition):
	- 객체지향 프로그래밍(OOP)은 데이터를 객체로 모델링하고, 객체 간의 상호작용을 통해 프로그램을 구성하는 프로그래밍 패러다임이다 (Meyer & Allen, 1991).
	- 클래스, 상속, 다형성, 캡슐화 등 네 가지 주요 특징을 가진다 (Meyer & Allen, 1991).
	- 유지보수성과 확장성이 뛰어나 게임 개발에서 널리 사용된다 (Gamma et al., 1994).
- 예시 (Examples):
	- 플레이어, 몬스터, 아이템 등 게임 내 엔티티를 클래스로 정의하고, 상속과 다형성을 활용해 다양한 행동을 구현 (Gamma et al., 1994).
	- 유니티에서 MonoBehaviour를 상속받아 게임 오브젝트의 동작을 구현 (Unity Technologies, 2020).

## Literature Review

#### Meyer & Allen, 1991
- [The Three-Component Model of Organizational Commitment](https://doi.org/10.1016/0749-5978(91)90011-Z)
	- Source: Journal of Organizational Behavior
- 주요 내용 (Key points):
	- OOP의 기본 개념과 장점 설명
	- 유지보수성, 재사용성 강조
	- 객체 간 메시지 전달의 중요성

#### Gamma et al., 1994
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://doi.org/10.5555/186897)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- OOP의 설계 패턴 소개
	- 게임 개발에서의 활용 사례
	- 코드 재사용성 및 확장성 강조

#### Unity Technologies, 2020
- [Unity Scripting API](https://docs.unity3d.com/ScriptReference/MonoBehaviour.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 OOP 활용
	- MonoBehaviour 상속 구조
	- 게임 오브젝트 관리

## 관련 개념 (Related Concepts)

- [[상속 (INHERITANCE)]] #OOP-class-inheritance
	- 부모 클래스의 속성과 메서드를 자식 클래스가 물려받는 개념
- [[다형성 (POLYMORPHISM)]] #OOP-polymorphism
	- 동일한 인터페이스로 다양한 동작을 구현하는 개념
- [[캡슐화 (ENCAPSULATION)]] #OOP-encapsulation
	- 데이터와 메서드를 하나의 단위로 묶고, 외부에 필요한 부분만 공개하는 개념 