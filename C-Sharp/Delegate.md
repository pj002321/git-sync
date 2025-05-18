
## 델리게이트 (DELEGATE)

#### What is Delegate

- 정의 (Definition):
	- 델리게이트는 메서드 참조를 저장하고 실행할 수 있는 타입으로, C#의 타입 안전한 함수 포인터이다 (Hejlsberg et al., 2003).
	- 이벤트 처리, 콜백 구현, 비동기 프로그래밍 등에서 활용된다 (Hejlsberg et al., 2003).
	- 게임 개발에서 오브젝트 간 통신, UI 이벤트 처리 등에 자주 사용된다 (Unity Technologies, 2020).
- 예시 (Examples):
	- 버튼 클릭 시 특정 메서드를 실행하는 이벤트 핸들러 (Unity Technologies, 2020).
	- AI 행동 트리에서 동적으로 행동을 바인딩 (Hejlsberg et al., 2003).

## Literature Review

#### Hejlsberg et al., 2003
- [The C# Programming Language](https://doi.org/10.5555/861282)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- 델리게이트의 정의와 사용법
	- 이벤트 및 콜백 구현 사례
	- 타입 안전성 강조

#### Unity Technologies, 2020
- [Unity Events](https://docs.unity3d.com/kr/2020.3/Manual/UnityEvents.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 델리게이트 및 이벤트 활용
	- UI, 게임 오브젝트 간 통신
	- 실시간 이벤트 처리

## 관련 개념 (Related Concepts)

- [[이벤트 (EVENT)]] #delegate-event
	- 특정 동작이 발생했을 때 실행되는 메서드 집합
- [[콜백 (CALLBACK)]] #delegate-callback
	- 특정 시점에 호출되는 함수 참조
- [[비동기 프로그래밍 (ASYNC PROGRAMMING)]] #delegate-async
	- 델리게이트를 활용한 비동기 작업 처리 