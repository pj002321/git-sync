
## 파괴하지 않음 (DontDestroyOnLoad)

#### What is DontDestroyOnLoad

- 정의 (Definition):
	- DontDestroyOnLoad는 씬이 전환되어도 GameObject를 파괴하지 않고 유지하는 메서드입니다. (Unity Documentation, 2024)
	- 게임 전체에서 유지되어야 하는 객체(예: 게임 매니저, 오디오 매니저 등)에 사용됩니다.

- 예시 (Examples):
	- 게임 매니저: 게임의 전반적인 상태를 관리
	- 오디오 매니저: 배경 음악 등 지속적인 오디오 관리
	- 데이터 매니저: 플레이어 데이터 등 저장 데이터 관리

## Literature Review

#### Unity Technologies, 2024
- [DontDestroyOnLoad](https://docs.unity3d.com/ScriptReference/Object.DontDestroyOnLoad.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- 씬 전환 시에도 객체가 유지됩니다.
	- 싱글톤 패턴과 함께 자주 사용됩니다.
	- 메모리 관리에 주의가 필요합니다.

## 관련 개념 (Related Concepts)
	- 씬 전환과 관련된 기능
	- 전역적으로 하나의 인스턴스만 유지하는 디자인 패턴
	- 게임의 전반적인 상태를 관리하는 매니저 


[[C-Sharp&Unity]]