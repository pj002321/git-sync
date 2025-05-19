---
tags:
- Unity
- Component
- Transform
- Position
- Rotation
aliases:
- Transform
- UnityTransform
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 트랜스폼 (Transform)

#### What is Transform

- 정의 (Definition):
	- Transform은 GameObject의 위치, 회전, 크기를 제어하는 기본 컴포넌트입니다. (Unity Documentation, 2024)
	- 모든 GameObject는 반드시 하나의 Transform 컴포넌트를 가집니다.

- 예시 (Examples):
	- transform.position: GameObject의 월드 좌표계 상의 위치
	- transform.rotation: GameObject의 회전값 (쿼터니언)
	- transform.localScale: GameObject의 크기

## Literature Review

#### Unity Technologies, 2024
- [Transform Component](https://docs.unity3d.com/ScriptReference/Transform.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Transform은 계층 구조를 지원합니다.
	- 로컬 좌표계와 월드 좌표계 간의 변환이 가능합니다.
	- 부모-자식 관계를 통한 상대적 변환이 가능합니다.

## 관련 개념 (Related Concepts)
	- Transform이 부착되는 기본 객체
	- 위치와 크기를 표현하는 3차원 벡터
	- 회전을 표현하는 수학적 구조 

[[C-Sharp&Unity]]