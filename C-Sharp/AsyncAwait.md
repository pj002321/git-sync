
## 비동기 프로그래밍 (ASYNC/AWAIT)

#### What is Async/Await

- 정의 (Definition):
	- Async/Await는 비동기 작업을 간결하게 작성할 수 있도록 지원하는 C#의 키워드이다 (Toub, 2012).
	- 비동기 메서드는 UI 멈춤 없이 네트워크, 파일 IO 등 장시간 작업을 처리할 수 있다 (Toub, 2012).
	- 게임 개발에서 네트워크 통신, 리소스 로딩, 대기 시간 최소화 등에 활용된다 (Unity Technologies, 2020).
- 예시 (Examples):
	- 서버에서 데이터를 받아올 때 await로 대기 (Toub, 2012).
	- Unity에서 Addressables, AssetBundle 비동기 로딩 (Unity Technologies, 2020).

## Literature Review

#### Toub, 2012
- [Async Programming with Async and Await](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/async/)
	- Source: Microsoft Docs
- 주요 내용 (Key points):
	- async/await의 기본 원리
	- 비동기 메서드 작성법
	- UI 멈춤 없는 작업 처리

#### Unity Technologies, 2020
- [Unity Manual: Async Operations](https://docs.unity3d.com/kr/2020.3/Manual/AsyncOperation.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 비동기 작업 처리
	- Addressables, AssetBundle 등 리소스 비동기 로딩
	- 게임 성능 최적화

## 관련 개념 (Related Concepts)

- [[Task]] #async-task
	- 비동기 작업을 나타내는 객체
- [[동시성 (CONCURRENCY)]] #async-concurrency
	- 여러 작업을 동시에 처리하는 개념
- [[스레드 (THREAD)]] #async-thread
	- OS 레벨에서 병렬로 실행되는 작업 단위 