---
tags:
-가비지컬렉션-GC-메모리관리-자동관리-최적화
-garbagecollection-memorymanagement-automatic-optimization-GC
-게임개발-면접-성능-최적화-메모리
aliases:
-GC
-가비지컬렉션
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 가비지 컬렉션 (GARBAGE COLLECTION, GC)

#### What is Garbage Collection

- 정의 (Definition):
	- 가비지 컬렉션(GC)은 더 이상 사용되지 않는 객체를 자동으로 탐지하고 메모리에서 해제하는 메커니즘이다 (Jones & Lins, 1996).
	- C#의 GC는 .NET 런타임에 내장되어 있으며, 메모리 누수 방지와 성능 최적화에 기여한다 (Microsoft, 2020).
	- 게임 개발에서 메모리 관리와 성능 최적화에 매우 중요하다 (Unity Technologies, 2020).
- 예시 (Examples):
	- 사용이 끝난 오브젝트가 자동으로 메모리에서 해제되는 경우 (Microsoft, 2020).
	- Unity에서 Instantiate/Destroy를 반복할 때 GC가 동작하여 메모리 회수 (Unity Technologies, 2020).

## Literature Review

#### Jones & Lins, 1996
- [Garbage Collection: Algorithms for Automatic Dynamic Memory Management](https://doi.org/10.5555/232634)
	- Source: Wiley
- 주요 내용 (Key points):
	- GC의 기본 원리와 알고리즘
	- 자동 메모리 관리의 장점
	- 성능 최적화 기법

#### Microsoft, 2020
- [Garbage Collection in .NET](https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/)
	- Source: Microsoft Docs
- 주요 내용 (Key points):
	- .NET의 GC 동작 방식
	- 메모리 누수 방지
	- 게임 개발에서의 주의점

#### Unity Technologies, 2020
- [Unity Manual: Automatic Memory Management](https://docs.unity3d.com/kr/2020.3/Manual/BestPracticeUnderstandingPerformanceInUnity1.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 GC 동작
	- Instantiate/Destroy와 GC의 관계
	- 성능 최적화 방법

## 관련 개념 (Related Concepts)

- [[메모리 관리 (MEMORY MANAGEMENT)]] #GC-memorymanagement
	- 메모리 할당과 해제를 효율적으로 관리하는 기법
- [[최적화 (OPTIMIZATION)]] #GC-optimization
	- 성능 향상을 위한 코드 및 메모리 관리
- [[참조 카운팅 (REFERENCE COUNTING)]] #GC-referencecounting
	- 객체 참조 수를 기반으로 메모리 해제 결정 