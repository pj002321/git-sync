---
tags:
-정점-변환-행렬-게임수학-그래픽스
-vertex-transformation-matrix-math-graphics
-게임개발-면접-좌표계-3D
aliases:
-정점변환
-VertexTransformation

## 정점 변환 (VERTEX TRANSFORMATION)

#### What is Vertex Transformation

- 정의 (Definition):
	- 정점 변환은 3D 모델의 정점 좌표를 다양한 공간(로컬, 월드, 뷰, 프로젝션)으로 변환하는 과정이다.
	- 행렬 곱셈을 통해 위치, 회전, 스케일, 투영 등 다양한 변환을 적용.
	- 그래픽스 파이프라인에서 필수적인 단계.

- 예시 (Examples):
	- Unity에서 localPosition → worldPosition → cameraPosition → clipPosition 순으로 변환.
	- DirectX HLSL에서 정점 변환 코드:
```hlsl
float4 worldPos = mul(float4(localPos, 1), World);
float4 viewPos = mul(worldPos, View);
float4 projPos = mul(viewPos, Projection);
```

## 주제별 세부 내용 정리와 설명
- **변환 단계**: 로컬→월드→뷰→프로젝션(클립)→스크린
- **행렬 곱셈 순서**: 변환 순서에 따라 결과 달라짐(Scale→Rotate→Translate 등)
- **좌표계**: 로컬(모델), 월드(장면), 뷰(카메라), 프로젝션(투영)
- **Unity 실전 팁**: Transform, Camera, Matrix4x4 등 활용
- **DirectX 실전 팁**: World/View/Projection 행렬, mul 함수 활용
- **현업 사례**: 본 애니메이션, 카메라 이동, 셰이더 내 정점 처리 등

## 예상 면접 질문과 답변
- Q. 정점 변환의 주요 단계는?
  A. 로컬→월드→뷰→프로젝션(클립)→스크린.
- Q. 행렬 곱셈 순서가 중요한 이유는?
  A. 변환 순서에 따라 최종 위치/방향이 달라짐.
- Q. Unity에서 정점 변환 활용 예시는?
  A. Transform, Camera, Matrix4x4 등으로 위치/회전/투영 제어.
- Q. DirectX에서 정점 변환을 구현하는 방법은?
  A. World/View/Projection 행렬 곱셈, mul 함수 활용.
- Q. 실무에서 정점 변환이 중요한 이유는?
  A. 모든 3D 렌더링/애니메이션/카메라 이동의 기초. 


[[GameMath]]
