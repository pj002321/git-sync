---
tags:
- Unity
- Async
- Loading
- Performance
- Programming
aliases:
- AsyncOperation
- UnityAsync
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 비동기 작업 (AsyncOperation)

#### What is AsyncOperation

- 정의 (Definition):
	- AsyncOperation은 Unity에서 비동기 작업의 진행 상태를 추적하는 클래스입니다. (Unity Documentation, 2024)
	- 씬 로딩, 에셋 번들 로딩 등 시간이 오래 걸리는 작업을 비동기적으로 처리할 때 사용됩니다.

- 예시 (Examples):
	- SceneManager.LoadSceneAsync(): 비동기적으로 씬을 로드
	- AssetBundle.LoadAssetAsync(): 비동기적으로 에셋을 로드
	- Resources.LoadAsync(): 비동기적으로 리소스를 로드

## Literature Review

#### Unity Technologies, 2024
- [AsyncOperation](https://docs.unity3d.com/ScriptReference/AsyncOperation.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- progress 속성으로 진행률을 확인할 수 있습니다.
	- isDone 속성으로 작업 완료 여부를 확인할 수 있습니다.
	- allowSceneActivation으로 씬 활성화 시점을 제어할 수 있습니다.

[[C-Sharp&Unity]]