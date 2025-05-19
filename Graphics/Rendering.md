

## 렌더링 (RENDERING)

#### What is Rendering

- 정의 (Definition):
	- 렌더링은 3D/2D 장면의 데이터를 이미지로 변환하는 과정이다.
	- 실시간 렌더링(게임, 시뮬레이션)과 오프라인 렌더링(영화, VFX)으로 구분된다.
	- 파이프라인, 셰이더, 조명, 텍스처링 등 다양한 기술이 결합된다.

- 예시 (Examples):
	- 게임에서 플레이어의 시점에 따라 실시간으로 장면을 그리는 과정.
	- 영화에서 고품질 이미지를 생성하는 오프라인 렌더링.

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

## 주제별 세부 내용 정리와 설명

- 실시간 렌더링 vs 오프라인 렌더링: 실시간은 빠른 속도, 오프라인은 품질 중시.
- 렌더링 파이프라인(DirectX/Unity): DirectX는 저수준 제어, Unity는 다양한 API 추상화 및 SRP 지원.
- 셰이더와 머티리얼: 셰이더는 GPU에서 실행, 머티리얼은 셰이더+속성.
- 조명, 그림자, 텍스처링, 포스트 프로세싱: 현실감과 시각 효과를 위한 핵심 요소.
- Unity의 SRP, URP, HDRP: 렌더링 커스터마이즈와 품질/성능 선택.
- DirectX의 HLSL: 셰이더 직접 작성, 세밀한 제어 가능.

## 예상 면접 질문과 답변

- Q. 실시간 렌더링과 오프라인 렌더링의 차이는?
  A. 실시간은 빠른 속도로 즉시 이미지를 생성(게임 등), 오프라인은 품질을 중시해 긴 시간 연산(영화 등)합니다.
- Q. 렌더링 파이프라인의 주요 단계는?
  A. 입력 어셈블리, 버텍스 처리, 래스터화, 픽셀 처리, 출력 병합 등입니다.
- Q. Unity에서 SRP와 URP, HDRP의 차이점은?
  A. SRP는 커스터마이즈 가능한 파이프라인, URP는 범용/경량, HDRP는 고품질 렌더링에 특화되어 있습니다.
- Q. DirectX에서 셰이더를 작성할 때 주의할 점은?
  A. HLSL 문법, 최적화, 하드웨어 호환성, 파이프라인 단계별 역할을 고려해야 합니다.
- Q. 게임에서 렌더링 최적화 방법은?
  A. 드로우콜 최소화, LOD, 배칭, 셰이더 최적화, 불필요한 연산 제거 등이 있습니다. 

[[Graphics]]