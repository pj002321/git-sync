---
tags:
-텍스처링-그래픽스-샘플링-UV-맵핑
-texturing-graphics-sampling-uv-mapping
-게임개발-면접-머티리얼-이미지
aliases:
-텍스처링
-Texturing

## 텍스처링 과정 (TEXTURING)

#### What is Texturing

- 정의 (Definition):
	- 텍스처링은 2D 이미지를 3D 모델 표면에 입혀 사실감과 디테일을 부여하는 그래픽스 과정이다.
	- UV 좌표(텍스처 좌표)를 통해 3D 정점/프레그먼트에 2D 이미지 매핑.
	- 샘플링, 필터링, 랩핑 등 다양한 기법이 존재.

- 예시 (Examples):
	- Unity에서 머티리얼(Material)에 텍스처(Texture2D) 할당:
```csharp
material.mainTexture = texture;
```
	- DirectX HLSL에서 텍스처 샘플링 코드:
```hlsl
float4 color = tex2D(sampler, uv);
```
	- UV 언랩(Unwrap)로 3D 모델에 2D 텍스처 좌표 부여

## 주제별 세부 내용 정리와 설명
- **UV 맵핑**: 3D 정점/프레그먼트에 2D 텍스처 좌표 할당
- **샘플링/필터링**: Nearest, Bilinear, Trilinear, Anisotropic 등
- **랩핑/클램핑**: 텍스처 좌표 범위 밖 처리(반복, 경계 등)
- **Unity 실전 팁**: Material, Texture2D, Shader에서 _MainTex, Tiling/Offset 등 활용
- **DirectX 실전 팁**: SamplerState, Texture2D, HLSL tex2D/tex.Sample 등
- **현업 사례**: 캐릭터/배경 텍스처, UI, 라이트맵, 노멀맵 등

## 예상 면접 질문과 답변
- Q. 텍스처링이란?
  A. 2D 이미지를 3D 표면에 입혀 사실감을 부여하는 과정.
- Q. UV 맵핑이란?
  A. 3D 정점/프레그먼트에 2D 텍스처 좌표를 할당하는 것.
- Q. 텍스처 샘플링/필터링의 종류는?
  A. Nearest, Bilinear, Trilinear, Anisotropic 등.
- Q. Unity에서 텍스처링 활용 예시는?
  A. Material, Texture2D, Shader에서 _MainTex 등.
- Q. DirectX에서 텍스처 샘플링 구현 방법은?
  A. SamplerState, tex2D/tex.Sample 등 활용. 