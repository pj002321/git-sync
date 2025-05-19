

## 컴퓨터 그래픽스 (COMPUTER GRAPHICS)

#### What is Computer Graphics

- 정의 (Definition):
	- 컴퓨터 그래픽스는 컴퓨터를 이용해 2D/3D 이미지, 애니메이션, 시각 효과를 생성·처리·표시하는 기술 및 학문이다.
	- 주요 분야: 렌더링, 모델링, 애니메이션, 조명, 텍스처링, 파이프라인, 셰이더 등.
	- 실시간(게임, 시뮬레이션)과 오프라인(영화, VFX) 그래픽스로 구분.
	- 대표적 파이프라인: Vertex → Rasterization → Fragment/Pixel → Output.

- 예시 (Examples):
	- Unity에서 3D 캐릭터 모델링 후 실시간 렌더링으로 게임 화면 출력.
	- DirectX로 HLSL 셰이더를 작성해 실시간 반사/그림자 효과 구현.
	- 영화에서 레이트레이싱 기반 오프라인 렌더링으로 CG 장면 제작.

## 주제별 세부 내용 정리와 설명
- **그래픽스 파이프라인**: Vertex Shader(정점 변환), Rasterization(2D 변환), Pixel Shader(색상/조명), Output(합성)
- **실시간 vs 오프라인**: 실시간은 GPU 병렬 처리, 오프라인은 CPU/분산 렌더팜 활용(품질↑, 속도↓)
- **Unity 실전 팁**: SRP/URP/HDRP로 파이프라인 커스터마이즈, Lightmap/Probe로 최적화, Shader Graph로 시각적 셰이더 설계
- **DirectX 실전 팁**: HLSL로 저수준 셰이더/파이프라인 직접 제어, DXR로 레이트레이싱 구현
- **현업 사례**: AAA 게임은 실시간+베이크드 혼합, 영화는 오프라인 레이트레이싱, 모바일은 경량화/최적화 중시
- **Unity vs DirectX**: Unity는 고수준 자동화/최적화, DirectX는 저수준 커스텀/최적화 강점

## 예상 면접 질문과 답변
- Q. 실시간 그래픽스와 오프라인 그래픽스의 차이는?
  A. 실시간은 GPU 병렬 처리로 빠른 반응, 오프라인은 품질 중시로 긴 시간 연산.
- Q. 그래픽스 파이프라인의 주요 단계와 각 역할은?
  A. Vertex(정점 변환), Rasterization(2D 변환), Pixel(색상/조명), Output(합성) 등.
- Q. Unity와 DirectX의 그래픽스 처리 차이는?
  A. Unity는 자동화/최적화, DirectX는 저수준 커스텀/최적화.
- Q. 실무에서 그래픽스 최적화 방법은?
  A. 드로우콜 최소화, LOD, 배칭, 텍스처 압축, 셰이더 최적화 등.
- Q. 레이트레이싱과 래스터화의 차이는?
  A. 레이트레이싱은 광선 추적(고품질), 래스터화는 2D 변환(고속) 방식.

## Literature Review

#### Foley et al., 1996
- [Computer Graphics: Principles and Practice](https://dl.acm.org/doi/10.5555/551714)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- 컴퓨터 그래픽스의 기본 원리와 주요 알고리즘
	- 렌더링, 모델링, 변환, 조명 등 핵심 개념 설명
	- 실용적 응용 사례 다수 제시

#### Akenine-Möller et al., 2018
- [Real-Time Rendering, Fourth Edition](https://www.crcpress.com/Real-Time-Rendering-Fourth-Edition/Akenine-Moller-Haines-Hoffman/p/book/9781138627000)
	- Source: CRC Press
- 주요 내용 (Key points):
	- 실시간 렌더링의 최신 기술 동향
	- GPU 파이프라인, 셰이더, 최적화 기법
	- 게임 및 인터랙티브 미디어 응용

## 관련 개념 (Related Concepts)

	- 렌더링 : 3D/2D 장면을 이미지로 변환하는 과정
	- 파이프라인 : 그래픽스 처리의 단계적 흐름(모델링→변환→조명→렌더링)
	- 모델링 : 3D 오브젝트의 기하 구조를 정의하는 과정
	- 조명 : 장면 내 빛의 효과를 시뮬레이션하는 기술
	- 텍스쳐링 : 표면에 이미지를 입혀 사실감을 높이는 기법 

[[Graphics]]