---
tags:
- Unity
- Lifecycle
- MonoBehaviour
- Event
- Programming
aliases:
- UnityLifecycle
- MonoBehaviourLifecycle
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 유니티 생명주기 (Unity Lifecycle)

#### What is Unity Lifecycle

- 정의 (Definition):
	- Unity 생명주기는 MonoBehaviour 스크립트의 실행 순서와 이벤트 호출 시점을 정의합니다. (Unity Documentation, 2024)
	- 게임의 초기화, 업데이트, 종료 등 각 단계에서 호출되는 이벤트들을 포함합니다.

- 예시 (Examples):
	- Awake(): 스크립트가 로드될 때 호출
	- Start(): 첫 프레임 업데이트 전에 호출
	- Update(): 매 프레임마다 호출
	- OnDestroy(): 객체가 파괴될 때 호출

## Literature Review

#### Unity Technologies, 2024
- [Order of Execution for Event Functions](https://docs.unity3d.com/Manual/ExecutionOrder.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- 이벤트 함수들은 정해진 순서대로 실행됩니다.
	- 스크립트 실행 순서를 커스터마이즈할 수 있습니다.
	- 물리, 렌더링 등 시스템별로 다른 이벤트가 존재합니다.

## 관련 개념 (Related Concepts)

- [[MonoBehaviour (모노비헤이비어)]] #unity #scripting #component
	- 생명주기 이벤트를 제공하는 기본 클래스

- [[Event Function (이벤트 함수)]] #unity #event #programming
	- 생명주기의 각 단계에서 호출되는 함수

- [[Script Execution Order (스크립트 실행 순서)]] #unity #execution #order
	- 스크립트 간의 실행 순서를 제어하는 방법 