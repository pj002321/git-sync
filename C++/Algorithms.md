---
tags:
- C++
- STL
- Algorithms
- Containers
- Programming
aliases:
- STLAlgorithms
- CppAlgorithms
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## STL 알고리즘 (STL Algorithms)

#### What is STL Algorithms

- 정의 (Definition):
	- STL 알고리즘은 컨테이너의 요소들을 처리하기 위한 일반적인 알고리즘들의 모음입니다. (Stroustrup, 2013)
	- 반복자를 통해 컨테이너와 독립적으로 동작하며, 재사용성이 높습니다.

- 예시 (Examples):
	- 정렬: `sort()`, `stable_sort()`
	- 검색: `find()`, `binary_search()`
	- 수정: `transform()`, `replace()`
	- 수치: `accumulate()`, `inner_product()`
	- 분할: `partition()`, `stable_partition()`

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 알고리즘은 반복자를 통해 컨테이너와 분리됩니다.
	- 함수 객체와 람다를 사용할 수 있습니다.
	- 알고리즘의 복잡도가 보장됩니다.

## 관련 개념 (Related Concepts)

- [[Iterators (반복자)]] #cpp #iterators #stl
	- 알고리즘이 사용하는 반복자

- [[Function Objects (함수 객체)]] #cpp #function #objects
	- 알고리즘의 동작을 커스터마이즈하는 방법

- [[STL Containers (STL 컨테이너)]] #cpp #stl #containers
	- 알고리즘이 처리하는 데이터 구조 