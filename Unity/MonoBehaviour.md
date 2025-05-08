---
tags:
- Unity
- Scripting
- MonoBehaviour
- Component
- Programming
aliases:
- MonoBehaviour
- UnityScript
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## MonoBehaviour (모노비헤이비어)

#### What is MonoBehaviour

- 정의 (Definition):
	- MonoBehaviour는 Unity에서 스크립트를 작성할 때 상속받는 기본 클래스입니다. (Unity Documentation, 2024)
	- GameObject에 부착되어 동작을 제어하는 컴포넌트의 기본이 됩니다.

- 예시 (Examples):
	- Start(): 스크립트가 활성화될 때 한 번 호출됩니다.
	- Update(): 매 프레임마다 호출됩니다.
	- OnCollisionEnter(): 충돌이 발생할 때 호출됩니다.

## Literature Review

#### Unity Technologies, 2024
- [MonoBehaviour](https://docs.unity3d.com/ScriptReference/MonoBehaviour.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- MonoBehaviour는 Unity의 생명주기 이벤트를 처리합니다.
	- 컴포넌트 기반 아키텍처의 핵심 요소입니다.
	- 다양한 이벤트 함수를 제공합니다.

## 관련 개념 (Related Concepts)

- [[GameObject (게임오브젝트)]] #unity #gameobject #component
	- MonoBehaviour가 부착되는 기본 객체

- [[Component (컴포넌트)]] #unity #component #architecture
	- MonoBehaviour의 부모 클래스

- [[Coroutine (코루틴)]] #unity #coroutine #programming
	- MonoBehaviour에서 제공하는 비동기 실행 기능 