---
tags:
- C++
- Memory
- Management
- Interview
- Programming
aliases:
- MemoryManagement
- CppMemory
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 메모리 관리 (Memory Management)

#### What is Memory Management

- 정의 (Definition):
	- C++에서 메모리 관리는 동적으로 할당된 메모리의 생성과 해제를 제어하는 과정입니다. (Stroustrup, 2013)
	- new/delete 연산자를 사용하여 메모리를 수동으로 관리하거나, 스마트 포인터를 사용하여 자동으로 관리할 수 있습니다.

- 예시 (Examples):
	- 동적 메모리 할당: `int* ptr = new int(10);`
	- 메모리 해제: `delete ptr;`
	- 배열 할당: `int* arr = new int[10];`
	- 배열 해제: `delete[] arr;`

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 메모리 누수는 프로그램의 안정성을 해치는 주요 원인입니다.
	- RAII(Resource Acquisition Is Initialization) 패턴을 사용하여 메모리 관리를 자동화할 수 있습니다.
	- 스마트 포인터를 사용하여 메모리 관리를 더 안전하게 할 수 있습니다.

## 관련 개념 (Related Concepts)

- [[Smart Pointers (스마트 포인터)]] #cpp #memory #safety
	- 자동 메모리 관리를 제공하는 포인터 클래스

- [[RAII (자원 획득 초기화)]] #cpp #pattern #resource
	- 리소스의 수명을 객체의 수명에 바인딩하는 패턴

- [[Memory Leak (메모리 누수)]] #cpp #bug #memory
	- 할당된 메모리가 해제되지 않는 문제 