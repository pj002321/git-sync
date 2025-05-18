---
tags:
-그림자-연산-쉐도우맵-게임수학-그래픽스
-shadow-computation-shadowmap-math-graphics
-게임개발-면접-조명-최적화
aliases:
-그림자연산
-ShadowComputation

## 그림자 연산 (SHADOW COMPUTATION)

#### What is Shadow Computation

- 정의 (Definition):
	- 그림자 연산은 광원과 오브젝트의 위치/형상에 따라 그림자 영역을 계산하는 그래픽스/게임 엔진의 핵심 과정이다.
	- Shadow Map, Stencil Shadow, Ray Tracing 등 다양한 알고리즘 존재.
	- 실시간/오프라인 렌더링에서 품질과 성능의 균형이 중요.

- 예시 (Examples):
	- Unity에서 Shadow Map 기반 실시간 그림자 구현:
```csharp
// Light 컴포넌트에서 그림자 활성화
light.shadows = LightShadows.Soft;
```
	- DirectX HLSL에서 Shadow Map 샘플링 코드:
```hlsl
float shadow = tex2D(shadowMap, projCoords);
if (depth > shadow) color *= 0.5; // 그림자 영역
```
	- Stencil Buffer로 실루엣 그림자 구현

## 주제별 세부 내용 정리와 설명
- **Shadow Map**: 광원 시점에서 깊이맵 생성, 픽셀별 그림자 판정(실시간 표준)
- **Stencil Shadow**: 실루엣 기반, 고정밀/고비용(특수 효과)
- **Ray Tracing**: 광선 추적, 고품질/고비용(오프라인/최신 GPU)
- **Unity 실전 팁**: Light, Shadow Type, Quality Settings, Custom Shader 등
- **DirectX 실전 팁**: Shadow Map, Depth Bias, PCF(Soft Shadow) 등
- **현업 사례**: AAA 게임(실시간+베이크드 혼합), 모바일(최적화), 영화(고품질)

## 예상 면접 질문과 답변
- Q. Shadow Map의 원리는?
  A. 광원 시점에서 깊이맵 생성, 픽셀별로 그림자 판정.
- Q. Stencil Shadow와 Shadow Map의 차이는?
  A. Stencil은 실루엣 기반, Shadow Map은 깊이맵 기반.
- Q. Ray Tracing 그림자의 장단점은?
  A. 고품질/고비용, 실시간은 최신 GPU 필요.
- Q. Unity에서 그림자 품질/성능 조절 방법은?
  A. Quality Settings, Shadow Resolution, Custom Shader 등.
- Q. DirectX에서 그림자 연산 최적화 방법은?
  A. Depth Bias, PCF, Cascaded Shadow Map 등. 