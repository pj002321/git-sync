---
tags:
-LINQ-쿼리-데이터-집계-람다
-LINQ-query-data-aggregation-lambda
-게임개발-면접-데이터처리-최적화
aliases:
-LINQ
-링크
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## LINQ (LANGUAGE INTEGRATED QUERY)

#### What is LINQ

- 정의 (Definition):
	- LINQ는 C#에 내장된 데이터 질의 언어로, 컬렉션, 데이터베이스, XML 등 다양한 데이터 소스에 일관된 방식으로 쿼리를 수행할 수 있다 (Meijer et al., 2006).
	- 람다식, 메서드 체이닝 등 현대적 프로그래밍 패턴과 결합되어 사용된다 (Meijer et al., 2006).
	- 게임 개발에서 대량의 데이터 처리, 필터링, 집계 등에 활용된다 (Microsoft, 2020).
- 예시 (Examples):
	- 몬스터 리스트에서 HP가 0 이하인 객체만 필터링 (Microsoft, 2020).
	- 랭킹 시스템에서 상위 10명 추출 (Meijer et al., 2006).

## Literature Review

#### Meijer et al., 2006
- [LINQ: Reconciling Object, Relations and XML in the .NET Framework](https://doi.org/10.1145/1133255.1133267)
	- Source: SIGMOD
- 주요 내용 (Key points):
	- LINQ의 설계 목적과 장점
	- 다양한 데이터 소스에 대한 일관된 쿼리 제공
	- 람다식과의 결합

#### Microsoft, 2020
- [LINQ (Language Integrated Query)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/)
	- Source: Microsoft Docs
- 주요 내용 (Key points):
	- LINQ의 기본 문법과 사용법
	- 게임 개발에서의 데이터 처리 사례
	- 성능 및 최적화 팁

## 관련 개념 (Related Concepts)

- [[람다식 (LAMBDA EXPRESSION)]] #LINQ-lambda
	- 익명 함수로, 간결하게 동작을 표현하는 문법
- [[집계 (AGGREGATION)]] #LINQ-aggregation
	- 여러 데이터를 하나로 요약하는 연산
- [[컬렉션 (COLLECTION)]] #LINQ-collection
	- 데이터를 저장하고 관리하는 자료구조 