---
tags:
-파이프라인-그래픽스-렌더링-단계-구조
-pipeline-graphics-rendering-stage-structure
-게임개발-면접-DirectX-Unity
aliases:
-파이프라인
-Pipeline
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 파이프라인 (PIPELINE)

#### What is Pipeline

- 정의 (Definition):
	- 그래픽스 파이프라인은 3D/2D 데이터를 이미지로 변환하는 일련의 처리 단계이다 (Foley et al., 1996).
	- 주요 단계로 입력 어셈블리, 버텍스 처리, 래스터화, 픽셀 처리, 출력 병합 등이 있다 (Akenine-Möller et al., 2018).
	- 각 단계는 GPU에서 병렬로 처리되어 실시간 렌더링 성능을 높인다 (Akenine-Möller et al., 2018).
- 예시 (Examples):
	- 게임에서 카메라, 조명, 메시, 텍스처 등 다양한 요소가 파이프라인을 거쳐 최종 이미지로 출력 (Unity Technologies, 2020).

## Literature Review

#### Foley et al., 1996
- [Computer Graphics: Principles and Practice](https://dl.acm.org/doi/10.5555/551714)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- 파이프라인의 단계별 구조와 역할
	- 실시간 렌더링에서의 중요성
	- GPU 병렬 처리의 원리

#### Akenine-Möller et al., 2018
- [Real-Time Rendering, Fourth Edition](https://www.crcpress.com/Real-Time-Rendering-Fourth-Edition/Akenine-Moller-Haines-Hoffman/p/book/9781138627000)
	- Source: CRC Press
- 주요 내용 (Key points):
	- 파이프라인의 최신 구조
	- 프로그래머블 셰이더의 도입
	- 게임 엔진에서의 파이프라인 응용

#### Unity Technologies, 2020
- [Unity Manual: Scriptable Render Pipeline](https://docs.unity3d.com/kr/2020.3/Manual/ScriptableRenderPipeline.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity의 SRP 구조와 특징
	- 파이프라인 커스터마이즈 방법
	- 다양한 렌더링 방식 지원

## 주제별 세부 내용 정리
- 파이프라인의 주요 단계(입력, 버텍스, 래스터화, 픽셀, 출력)
- DirectX의 고정/프로그래머블 파이프라인
- Unity의 SRP 구조
- GPU 병렬 처리
- 각 단계별 역할과 최적화

#### DirectX와 Unity에서의 파이프라인
- DirectX는 고정 및 프로그래머블 파이프라인 구조를 제공하며, 개발자가 각 단계를 세밀하게 제어할 수 있다.
- Unity는 내부적으로 다양한 그래픽 API(DirectX, OpenGL 등)를 추상화하여 파이프라인을 구성한다.
- Unity의 SRP(Scriptable Render Pipeline)는 파이프라인의 각 단계를 커스터마이즈할 수 있게 해준다.

## 예상 면접 질문
- 그래픽스 파이프라인의 주요 단계는?
- DirectX와 Unity의 파이프라인 구조 차이는?
- SRP의 장점은?
- 각 단계별로 최적화할 수 있는 방법은?
- 래스터화와 레이트레이싱의 차이는?
