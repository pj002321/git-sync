---
tags:
- C++
- Memory
- Leak
- Bug
- Debugging
aliases:
- MemoryLeak
- CppMemoryLeak
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 메모리 누수 (Memory Leak)

#### What is Memory Leak

- 정의 (Definition):
	- 메모리 누수는 동적으로 할당된 메모리가 더 이상 필요하지 않을 때 해제되지 않는 현상입니다. (Stroustrup, 2013)
	- 프로그램이 실행되는 동안 계속해서 메모리를 소모하게 되어 결국 시스템 리소스를 고갈시킬 수 있습니다.

- 예시 (Examples):
	- delete 누락: `int* ptr = new int(10); // delete ptr; 누락`
	- 예외 발생: try 블록에서 메모리 할당 후 예외 발생
	- 순환 참조: shared_ptr의 순환 참조로 인한 메모리 누수

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 메모리 누수는 프로그램의 안정성을 해치는 주요 원인입니다.
	- 스마트 포인터를 사용하여 메모리 누수를 방지할 수 있습니다.
	- 메모리 누수 검출 도구를 사용하여 문제를 찾을 수 있습니다.

## 관련 개념 (Related Concepts)

- [[Smart Pointers (스마트 포인터)]] #cpp #memory #safety
	- 메모리 누수를 방지하는 자동 메모리 관리

- [[RAII (자원 획득 초기화)]] #cpp #pattern #resource
	- 리소스의 자동 해제를 보장하는 패턴

- [[Memory Debugging (메모리 디버깅)]] #cpp #debug #memory
	- 메모리 누수를 찾고 해결하는 방법 


[[C++]]  