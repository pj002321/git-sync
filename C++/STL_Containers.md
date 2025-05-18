---
tags:
- C++
- STL
- Containers
- DataStructures
- Algorithms
aliases:
- STLContainers
- CppSTL
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## STL 컨테이너 (STL Containers)

#### What is STL Containers

- 정의 (Definition):
	- STL(Standard Template Library) 컨테이너는 데이터를 저장하고 관리하는 자료구조입니다. (Stroustrup, 2013)
	- 시퀀스 컨테이너, 연관 컨테이너, 컨테이너 어댑터 등으로 분류됩니다.

- 예시 (Examples):
	- 시퀀스 컨테이너: vector, list, deque
	- 연관 컨테이너: map, set, unordered_map
	- 컨테이너 어댑터: stack, queue, priority_queue

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 각 컨테이너는 특정 사용 사례에 최적화되어 있습니다.
	- 반복자(iterator)를 통해 컨테이너의 요소에 접근할 수 있습니다.
	- 알고리즘 라이브러리와 함께 사용하여 강력한 기능을 제공합니다.

## 관련 개념 (Related Concepts)

- [[Iterators (반복자)]] #cpp #stl #iteration
	- 컨테이너의 요소에 접근하는 방법

- [[Algorithms (알고리즘)]] #cpp #stl #algorithms
	- 컨테이너의 데이터를 처리하는 함수들

- [[Templates (템플릿)]] #cpp #generic #programming
	- STL의 기본이 되는 제네릭 프로그래밍 기능 


[[C++]]  