---
tags:
- Unity
- Programming
- Coroutine
- Async
- Performance
aliases:
- Coroutine
- UnityCoroutine
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 코루틴 (Coroutine)

#### What is Coroutine

- 정의 (Definition):
	- 코루틴은 Unity에서 비동기 작업을 처리하기 위한 특별한 함수입니다. (Unity Documentation, 2024)
	- 실행을 일시 중지하고 나중에 다시 시작할 수 있는 기능을 제공합니다.

- 예시 (Examples):
	- yield return new WaitForSeconds(1f): 1초 동안 실행을 일시 중지합니다.
	- yield return new WaitForEndOfFrame(): 프레임이 끝날 때까지 대기합니다.
	- yield return null: 다음 프레임까지 대기합니다.

## Literature Review

#### Unity Technologies, 2024
- [Coroutines](https://docs.unity3d.com/Manual/Coroutines.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- 코루틴은 MonoBehaviour에서만 사용할 수 있습니다.
	- StartCoroutine() 메서드로 시작합니다.
	- StopCoroutine() 메서드로 중지할 수 있습니다.

## 관련 개념 (Related Concepts)

- [[MonoBehaviour (모노비헤이비어)]] #unity #scripting #component
	- 코루틴을 사용할 수 있는 기본 클래스

- [[AsyncOperation (비동기 작업)]] #unity #async #programming
	- 비동기 작업을 처리하는 클래스

- [[Yield (양보)]] #unity #programming #coroutine
	- 코루틴에서 실행을 일시 중지하는 키워드 