---
tags:
-조명-그래픽스-빛-렌더링-실시간
-lighting-graphics-light-rendering-realtime
-게임개발-면접-DirectX-Unity
aliases:
-조명
-Lighting
CMDS: "[[:books: 104 Terminologies]]"
index: "[[:label: Research Notes]]"
author: "[[AI Assistant]]"
---

## 조명 (LIGHTING)

#### What is Lighting

- 정의 (Definition):
	- 조명은 3D/2D 장면 내에서 빛의 효과를 시뮬레이션하여 현실감과 분위기를 부여하는 그래픽스 기술이다 (Foley et al., 1996).
	- 광원, 그림자, 반사, 굴절 등 다양한 요소가 포함된다 (Akenine-Möller et al., 2018).
	- 실시간 조명, 베이크드 조명, 글로벌 일루미네이션 등 다양한 방식이 있다 (Akenine-Möller et al., 2018).
- 예시 (Examples):
	- 게임에서 플레이어가 손전등을 켰을 때 주변이 밝아지는 효과 (Unity Technologies, 2020).
	- 실시간 그림자, 반사, PBR(물리 기반 렌더링) 조명 (Akenine-Möller et al., 2018).

#### DirectX와 Unity에서의 조명
- DirectX는 개발자가 HLSL로 직접 조명 모델을 구현할 수 있다.
- Unity는 다양한 조명 타입(Point, Spot, Directional 등)과 실시간/베이크드 조명, GI(Global Illumination) 시스템을 제공한다.
- Unity의 Lighting 시스템은 엔진 내부에서 최적화 및 자동화되어 있다.

## Literature Review

#### Foley et al., 1996
- [Computer Graphics: Principles and Practice](https://dl.acm.org/doi/10.5555/551714)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- 조명의 기본 원리와 모델
	- 현실감 있는 장면 구현 방법
	- 다양한 조명 효과 설명

#### Akenine-Möller et al., 2018
- [Real-Time Rendering, Fourth Edition](https://www.crcpress.com/Real-Time-Rendering-Fourth-Edition/Akenine-Moller-Haines-Hoffman/p/book/9781138627000)
	- Source: CRC Press
- 주요 내용 (Key points):
	- 실시간 조명과 베이크드 조명
	- PBR, GI 등 최신 조명 기술
	- 게임 엔진에서의 응용

#### Unity Technologies, 2020
- [Unity Manual: Lighting](https://docs.unity3d.com/kr/2020.3/Manual/LightingSection.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity의 조명 시스템 구조
	- 실시간/베이크드 조명, GI 지원
	- 최적화 및 자동화 기능

## 관련 개념 (Related Concepts)

- [[광원 (LIGHT SOURCE)]] #lighting-source
	- 장면 내 빛을 생성하는 요소
- [[그림자 (SHADOW)]] #lighting-shadow
	- 빛에 의해 생성되는 어두운 영역
- [[반사 (REFLECTION)]] #lighting-reflection
	- 표면에서 빛이 반사되는 효과
- [[글로벌 일루미네이션 (GLOBAL ILLUMINATION)]] #lighting-GI
	- 간접광, 다중 반사 등 현실감 있는 조명
- [[PBR (PHYSICALLY BASED RENDERING)]] #lighting-PBR
	- 물리 기반의 조명 및 재질 표현 