---
tags:
-이벤트-델리게이트-리스너-이벤트버스-비동기
-event-delegate-listener-eventbus-async
-게임개발-면접-이벤트처리-구조
aliases:
-이벤트
-Event
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 이벤트 (EVENT)

#### What is Event

- 정의 (Definition):
	- 이벤트는 특정 동작이 발생했을 때 실행되는 메서드 집합을 의미하며, 델리게이트를 기반으로 동작한다 (Hejlsberg et al., 2003).
	- UI, 게임 오브젝트 간 상호작용, 네트워크 통신 등에서 활용된다 (Unity Technologies, 2020).
	- 게임 개발에서 실시간 반응형 시스템 구현에 필수적이다 (Unity Technologies, 2020).
- 예시 (Examples):
	- 플레이어가 버튼을 클릭할 때 UI가 반응하는 경우 (Unity Technologies, 2020).
	- 몬스터가 사망 시 경험치 지급 이벤트 발생 (Hejlsberg et al., 2003).

## Literature Review

#### Hejlsberg et al., 2003
- [The C# Programming Language](https://doi.org/10.5555/861282)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- 이벤트와 델리게이트의 관계
	- 이벤트 선언 및 구독 방법
	- 실시간 시스템에서의 활용

#### Unity Technologies, 2020
- [Unity Events](https://docs.unity3d.com/kr/2020.3/Manual/UnityEvents.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 이벤트 처리 구조
	- UI, 게임 오브젝트 간 통신
	- 실시간 반응형 시스템 구현

## 관련 개념 (Related Concepts)

- [[델리게이트 (DELEGATE)]] #event-delegate
	- 이벤트의 기반이 되는 타입 안전 함수 포인터
- [[리스너 (LISTENER)]] #event-listener
	- 이벤트를 구독하고 처리하는 객체
- [[이벤트 버스 (EVENT BUS)]] #event-eventbus
	- 여러 이벤트를 중앙에서 관리하고 분배하는 구조 