---
tags:
-프레그먼트-출력병합-픽셀-블렌딩-그래픽스
-fragment-output-pixel-blending-graphics
-게임개발-면접-파이프라인-렌더링
aliases:
-프레그먼트
-FragmentProcessing
-출력병합
-OutputMerger

## 프레그먼트 처리와 출력 병합 (FRAGMENT PROCESSING & OUTPUT MERGER)

#### What is Fragment Processing & Output Merger

- 정의 (Definition):
	- 프레그먼트 처리는 래스터화 이후 각 픽셀 후보(프레그먼트)에 대해 색상, 조명, 텍스처, 깊이 등 최종 값을 계산하는 과정이다.
	- 출력 병합(Output Merger)은 여러 렌더 타겟(프레임버퍼)에 프레그먼트 결과를 합성(블렌딩, 깊이/스텐실 테스트 등)하는 단계다.
	- 픽셀 셰이더(DirectX)/프래그먼트 셰이더(OpenGL/Unity)에서 구현.

- 예시 (Examples):
	- Unity에서 Surface Shader/Fragment Shader로 픽셀별 조명/텍스처 처리.
	- DirectX HLSL에서 픽셀 셰이더와 Output Merger 블렌딩 코드:
```hlsl
float4 PSMain(...) : SV_Target {
    float4 color = ...; // 조명/텍스처 결과
    return color;
}
// Output Merger에서 블렌딩 설정
OMSetBlendState(...);
```

## 주제별 세부 내용 정리와 설명
- **프레그먼트 vs 픽셀**: 프레그먼트는 후보, 픽셀은 최종 출력(깊이/스텐실/블렌딩 통과 시)
- **블렌딩**: 여러 레이어/반투명/후처리 효과 구현(Alpha Blending 등)
- **깊이/스텐실 테스트**: Z-buffer, Stencil Buffer로 픽셀 가시성/마스킹 결정
- **Unity 실전 팁**: Surface Shader, Blend, ZTest, Stencil 등 활용
- **DirectX 실전 팁**: Pixel Shader, OMSetBlendState, Depth/Stencil State 등
- **현업 사례**: 투명/반투명 효과, 그림자/포스트 프로세싱, UI 합성 등

## 예상 면접 질문과 답변
- Q. 프레그먼트와 픽셀의 차이는?
  A. 프레그먼트는 후보, 픽셀은 최종 출력(테스트 통과 시).
- Q. 블렌딩이란?
  A. 여러 색상/레이어를 합성하는 과정(Alpha Blending 등).
- Q. 깊이/스텐실 테스트의 역할은?
  A. 픽셀 가시성/마스킹 결정.
- Q. Unity에서 프레그먼트/출력 병합 활용 예시는?
  A. Surface Shader, Blend, ZTest, Stencil 등.
- Q. DirectX에서 Output Merger를 제어하는 방법은?
  A. OMSetBlendState, Depth/Stencil State 등 활용. 