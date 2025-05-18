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
	- 조명은 3D/2D 장면 내에서 빛의 효과를 시뮬레이션하여 현실감과 분위기를 부여하는 그래픽스 기술이다.
	- 주요 요소로는 광원(Light Source), 그림자(Shadow), 반사(Reflection), 굴절(Refraction), 글로벌 일루미네이션(GI) 등이 있다.
	- 실시간 조명(Real-time Lighting)은 GPU에서 즉시 계산, 베이크드 조명(Baked Lighting)은 미리 계산해 성능을 높임.
	- 대표적 조명 모델로 Lambert, Phong, Blinn-Phong, PBR(Physically Based Rendering) 등이 있다.

- 예시 (Examples):
	- Unity에서 Point Light를 사용해 실시간 그림자와 반사 효과 구현.
	- DirectX HLSL로 Lambert 조명 모델을 구현하는 코드:
```hlsl
float3 normal = normalize(input.Normal);
float3 lightDir = normalize(lightPosition - input.Position);
float NdotL = max(dot(normal, lightDir), 0);
float3 diffuse = NdotL * lightColor * materialColor;
```
	- 베이크드 GI를 활용해 실내 장면의 간접광을 미리 계산하여 성능 최적화.

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

## 주제별 세부 내용 정리와 설명
- **조명 모델 수식**: Lambert(확산) = max(0, N·L), Phong(반사) = (R·V)^n 등.
- **실시간 vs 베이크드**: 실시간은 동적 오브젝트/광원에 적합, 베이크드는 정적 환경에 적합(성능↑, 유연성↓).
- **Unity 실전 팁**: 실시간 조명은 광원 수 제한, 베이크드 조명은 Lightmap 해상도와 UV 언랩에 주의. URP/HDRP에서 다양한 조명 옵션 제공.
- **DirectX 실전 팁**: HLSL로 다양한 조명 모델 직접 구현, 그림자 맵핑/반사/굴절 등 고급 효과는 별도 셰이더 필요.
- **현업 사례**: AAA 게임은 실시간+베이크드 혼합, 모바일은 베이크드 위주, VR/AR은 실시간 최적화 중요.
- **Unity vs DirectX**: Unity는 조명 시스템 자동화/최적화, DirectX는 저수준 제어와 커스텀 셰이더 강점.

## 예상 면접 질문과 답변
- Q. Lambert와 Phong 조명 모델의 차이는?
  A. Lambert는 확산 반사만, Phong은 확산+정반사(하이라이트)까지 표현.
- Q. 실시간 조명과 베이크드 조명의 장단점은?
  A. 실시간은 동적/유연, 성능 부담. 베이크드는 빠르고 품질↑, 동적 변화엔 부적합.
- Q. Unity에서 베이크드 GI를 쓸 때 주의점은?
  A. Lightmap 해상도, UV 언랩, 정적/동적 오브젝트 구분, 빛샘/아티팩트 방지.
- Q. DirectX에서 그림자 맵핑을 구현하려면?
  A. Depth map 생성, 셰이더에서 Shadow map 샘플링, Bias/Filtering 등 추가 구현 필요.
- Q. 실무에서 조명 최적화 방법은?
  A. 광원 수 제한, 베이크드 활용, 동적 그림자 최소화, LOD, Light Probe/Reflection Probe 적극 활용. 