---
tags:
-셰이더-GPU-렌더링-그래픽스-프로그램
-shader-gpu-rendering-graphics-program
-게임개발-면접-DirectX-Unity
aliases:
-셰이더
-Shader
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 셰이더 (SHADER)

#### What is Shader

- 정의 (Definition):
	- 셰이더는 GPU에서 실행되어 그래픽스 파이프라인의 각 단계를 제어하는 작은 프로그램이다 (Akenine-Möller et al., 2018).
	- 버텍스 셰이더, 픽셀(프래그먼트) 셰이더, 지오메트리 셰이더 등 다양한 종류가 있다 (Akenine-Möller et al., 2018).
	- 실시간 그래픽스에서 다양한 시각 효과와 최적화를 구현하는 데 필수적이다 (Akenine-Möller et al., 2018).
- 예시 (Examples):
	- 물리 기반 렌더링(PBR) 구현 (Unity Technologies, 2020).
	- 그림자, 반사, 포스트 프로세싱 효과 등 (Akenine-Möller et al., 2018).

## Literature Review

#### Akenine-Möller et al., 2018
- [Real-Time Rendering, Fourth Edition](https://www.crcpress.com/Real-Time-Rendering-Fourth-Edition/Akenine-Moller-Haines-Hoffman/p/book/9781138627000)
	- Source: CRC Press
- 주요 내용 (Key points):
	- 셰이더의 종류와 역할
	- 실시간 렌더링에서의 활용
	- 최적화 및 고급 효과 구현

#### Unity Technologies, 2020
- [Unity Manual: Shaders](https://docs.unity3d.com/kr/2020.3/Manual/Shaders.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 셰이더 작성 방식
	- Shader Graph, HLSL, ShaderLab 등
	- 커스터마이즈와 최적화

## 주제별 세부 내용 정리
- 셰이더의 종류(버텍스, 픽셀, 지오메트리 등)
- HLSL, ShaderLab, Shader Graph
- 머티리얼과 셰이더의 관계
- 실시간 효과(그림자, 반사, PBR 등)
- 최적화 기법

#### DirectX와 Unity에서의 셰이더
- DirectX에서는 HLSL(High Level Shader Language)로 셰이더를 작성한다.
- Unity에서는 ShaderLab, HLSL, Cg, C# 등 다양한 방식으로 셰이더를 작성할 수 있다.
- Unity의 Shader Graph를 사용하면 시각적으로 셰이더를 설계할 수 있다.
- DirectX는 저수준 제어가 가능하지만, Unity는 엔진 구조에 맞춘 추상화와 편의 기능을 제공한다.

## 예상 면접 질문
- 버텍스 셰이더와 픽셀 셰이더의 차이는?
- Unity에서 Shader Graph의 장점은?
- DirectX에서 셰이더 최적화 방법은?
- 머티리얼과 셰이더의 관계는?
- 실시간 렌더링에서 셰이더가 중요한 이유는? 