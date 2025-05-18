---
tags:
-렌더링-그래픽스-이미지생성-파이프라인-실시간
-rendering-graphics-image-pipeline-realtime
-게임개발-면접-DirectX-Unity
aliases:
-렌더링
-Rendering
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 렌더링 (RENDERING)

#### What is Rendering

- 정의 (Definition):
	- 렌더링은 3D/2D 장면의 데이터를 이미지로 변환하는 과정이다 (Foley et al., 1996).
	- 실시간 렌더링(게임, 시뮬레이션)과 오프라인 렌더링(영화, VFX)으로 구분된다 (Akenine-Möller et al., 2018).
	- 파이프라인, 셰이더, 조명, 텍스처링 등 다양한 기술이 결합된다 (Akenine-Möller et al., 2018).
- 예시 (Examples):
	- 게임에서 플레이어의 시점에 따라 실시간으로 장면을 그리는 과정 (Unity Technologies, 2020).
	- 영화에서 고품질 이미지를 생성하는 오프라인 렌더링 (Foley et al., 1996).

## Literature Review

#### Foley et al., 1996
- [Computer Graphics: Principles and Practice](https://dl.acm.org/doi/10.5555/551714)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- 렌더링의 기본 원리와 알고리즘
	- 실시간/오프라인 렌더링의 차이
	- 파이프라인 구조 설명

#### Akenine-Möller et al., 2018
- [Real-Time Rendering, Fourth Edition](https://www.crcpress.com/Real-Time-Rendering-Fourth-Edition/Akenine-Moller-Haines-Hoffman/p/book/9781138627000)
	- Source: CRC Press
- 주요 내용 (Key points):
	- 실시간 렌더링의 최신 기술
	- GPU 파이프라인, 셰이더, 최적화
	- 게임 엔진에서의 응용

#### Unity Technologies, 2020
- [Unity Manual: Rendering](https://docs.unity3d.com/kr/2020.3/Manual/RenderingSection.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity의 렌더링 파이프라인 구조
	- SRP, URP, HDRP 등 다양한 렌더링 방식
	- 커스터마이즈와 최적화

## 주제별 세부 내용 정리

- 실시간 렌더링 vs 오프라인 렌더링
- 렌더링 파이프라인(DirectX/Unity)
- 셰이더와 머티리얼
- 조명, 그림자, 텍스처링, 포스트 프로세싱
- Unity의 SRP, URP, HDRP
- DirectX의 HLSL, 저수준 제어

#### DirectX와 Unity에서의 렌더링
- DirectX는 Windows 기반의 저수준 그래픽 API로, 개발자가 파이프라인의 세부를 직접 제어할 수 있다.
- Unity는 고수준 엔진으로, 내부적으로 DirectX/OpenGL/Vulkan 등 다양한 API를 추상화하여 제공한다.
- Unity의 Scriptable Render Pipeline(SRP)은 개발자가 렌더링 과정을 커스터마이즈할 수 있게 해준다.
- DirectX에서는 HLSL을, Unity에서는 HLSL/ShaderLab/C#을 사용해 셰이더를 작성한다.

## 예상 면접 질문
- 실시간 렌더링과 오프라인 렌더링의 차이는?
- 렌더링 파이프라인의 주요 단계는?
- Unity에서 SRP와 URP, HDRP의 차이점은?
- DirectX에서 셰이더를 작성할 때 주의할 점은?
- 게임에서 렌더링 최적화 방법은? 