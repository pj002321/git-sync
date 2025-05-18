---
tags:
- C++
- ModernCpp
- Cpp11
- Cpp14
- Cpp17
aliases:
- ModernCpp
- CppModern
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 모던 C++ 기능 (Modern C++ Features)

#### What is Modern C++ Features

- 정의 (Definition):
	- C++11 이후 도입된 새로운 언어 기능들을 모던 C++ 기능이라고 합니다. (Stroustrup, 2013)
	- 코드의 안전성, 가독성, 성능을 향상시키는 다양한 기능들을 포함합니다.

- 예시 (Examples):
	- 자동 타입 추론: auto, decltype
	- 범위 기반 for 루프: for (auto& item : container)
	- 람다 표현식: [](int x) { return x * x; }
	- 이동 의미론: std::move, std::forward

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- C++11은 언어의 큰 변화를 가져왔습니다.
	- C++14, C++17은 추가적인 기능을 제공합니다.
	- 모던 C++은 더 안전하고 효율적인 코드 작성을 가능하게 합니다.

## 관련 개념 (Related Concepts)

- [[Smart Pointers (스마트 포인터)]] #cpp #memory #safety
	- C++11에서 도입된 자동 메모리 관리 기능

- [[Move Semantics (이동 의미론)]] #cpp #performance #rvalue
	- 객체의 효율적인 이동을 위한 기능

- [[Lambda Expressions (람다 표현식)]] #cpp #functional #programming
	- 익명 함수를 정의하는 방법 

[[C++]]  