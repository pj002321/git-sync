---
tags:
-직렬화-데이터저장-네트워크-포맷-역직렬화
-serialization-datastorage-network-format-deserialization
-게임개발-면접-저장-통신
aliases:
-직렬화
-Serialization
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 직렬화 (SERIALIZATION)

#### What is Serialization

- 정의 (Definition):
	- 직렬화는 객체의 상태를 저장하거나 네트워크로 전송할 수 있도록 바이트 스트림으로 변환하는 과정이다 (Microsoft, 2020).
	- 역직렬화는 바이트 스트림을 다시 객체로 복원하는 과정이다 (Microsoft, 2020).
	- 게임 개발에서 저장, 로딩, 네트워크 통신 등에 필수적으로 사용된다 (Unity Technologies, 2020).
- 예시 (Examples):
	- 게임 세이브 데이터를 파일로 저장할 때 객체를 직렬화 (Microsoft, 2020).
	- 네트워크 멀티플레이에서 오브젝트 상태를 전송할 때 직렬화 (Unity Technologies, 2020).

## Literature Review

#### Microsoft, 2020
- [Serialization in .NET](https://docs.microsoft.com/en-us/dotnet/standard/serialization/)
	- Source: Microsoft Docs
- 주요 내용 (Key points):
	- .NET의 직렬화 방식(Binary, XML, JSON 등)
	- 직렬화/역직렬화의 장단점
	- 보안 및 성능 이슈

#### Unity Technologies, 2020
- [Unity Manual: Script Serialization](https://docs.unity3d.com/kr/2020.3/Manual/script-Serialization.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 직렬화 규칙
	- 커스텀 직렬화 구현 방법
	- 게임 저장 및 네트워크 통신 사례

## 관련 개념 (Related Concepts)

- [[역직렬화 (DESERIALIZATION)]] #serialization-deserialization
	- 직렬화된 데이터를 다시 객체로 복원하는 과정
- [[데이터 포맷 (DATA FORMAT)]] #serialization-format
	- 직렬화에 사용되는 데이터 표현 방식 (JSON, XML 등)
- [[저장 (SAVE)]] #serialization-save
	- 게임 데이터를 파일 등 외부 저장소에 기록하는 과정 