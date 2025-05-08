---
tags:
- Unity
- GameDevelopment
- GameObject
- Component
- Architecture
aliases:
- GameObject
- Component
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 게임오브젝트와 컴포넌트 (GameObject and Component)

#### What is GameObject and Component

- 정의 (Definition):
	- GameObject는 Unity 씬에서 존재하는 모든 객체의 기본 클래스입니다. (Unity Documentation, 2024)
	- Component는 GameObject에 부착되어 특정 기능을 제공하는 클래스입니다. (Unity Documentation, 2024)

- 예시 (Examples):
	- Transform 컴포넌트: 모든 GameObject의 기본 컴포넌트로, 위치, 회전, 크기를 제어합니다.
	- Rigidbody 컴포넌트: 물리 시뮬레이션을 위한 컴포넌트입니다.
	- Mesh Renderer 컴포넌트: 3D 모델을 화면에 표시하는 컴포넌트입니다.

## Literature Review

#### Unity Technologies, 2024
- [GameObject and Component](https://docs.unity3d.com/Manual/GameObjects.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- GameObject는 씬의 기본 구성 요소입니다.
	- Component를 통해 GameObject에 기능을 추가할 수 있습니다.
	- GetComponent() 메서드를 통해 컴포넌트에 접근할 수 있습니다.

## 관련 개념 (Related Concepts)

- [[Transform (트랜스폼)]] #unity #component #transform
	- GameObject의 위치, 회전, 크기를 제어하는 기본 컴포넌트

- [[Prefab (프리팹)]] #unity #prefab #asset
	- 재사용 가능한 GameObject 템플릿

- [[Scene (씬)]] #unity #scene #management
	- GameObject들이 존재하는 공간 