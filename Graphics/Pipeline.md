
## 파이프라인 (PIPELINE)

#### What is Pipeline

- 정의 (Definition):
	- 그래픽스 파이프라인은 3D/2D 데이터를 이미지로 변환하는 일련의 처리 단계 집합이다.
	- 주요 단계: 입력 어셈블리 → 버텍스 셰이더 → 래스터화 → 픽셀 셰이더 → 출력 병합.
	- 고정(Fixed) 파이프라인(과거) vs 프로그래머블(현대, 셰이더 기반) 파이프라인.

- 예시 (Examples):
	- DirectX11에서 Input Layout, Vertex Shader, Pixel Shader, Output Merger로 구성된 파이프라인 구현.
	- Unity SRP에서 커스텀 렌더 패스 추가로 파이프라인 확장.
	- 래스터화 단계에서 삼각형을 픽셀로 변환하는 알고리즘:
```c
// Barycentric coordinates로 픽셀 내부 판정
float w0 = EdgeFunction(v1, v2, p);
float w1 = EdgeFunction(v2, v0, p);
float w2 = EdgeFunction(v0, v1, p);
if (w0 >= 0 && w1 >= 0 && w2 >= 0) { /* 픽셀 내부 */ }
```

## Literature Review

#### Foley et al., 1996
- [Computer Graphics: Principles and Practice](https://dl.acm.org/doi/10.5555/551714)
	- Source: Addison-Wesley
- 주요 내용 (Key points):
	- 파이프라인의 단계별 구조와 역할
	- 실시간 렌더링에서의 중요성
	- GPU 병렬 처리의 원리

#### Akenine-Möller et al., 2018
- [Real-Time Rendering, Fourth Edition](https://www.crcpress.com/Real-Time-Rendering-Fourth-Edition/Akenine-Moller-Haines-Hoffman/p/book/9781138627000)
	- Source: CRC Press
- 주요 내용 (Key points):
	- 파이프라인의 최신 구조
	- 프로그래머블 셰이더의 도입
	- 게임 엔진에서의 파이프라인 응용

#### Unity Technologies, 2020
- [Unity Manual: Scriptable Render Pipeline](https://docs.unity3d.com/kr/2020.3/Manual/ScriptableRenderPipeline.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity의 SRP 구조와 특징
	- 파이프라인 커스터마이즈 방법
	- 다양한 렌더링 방식 지원

## 주제별 세부 내용 정리와 설명
- **파이프라인 단계별 이론**: 입력(정점/속성), 변환(월드/뷰/프로젝션), 래스터화(2D 변환), 픽셀(조명/색상), 출력(합성)
- **고정 vs 프로그래머블**: 고정은 하드웨어 내장, 프로그래머블은 셰이더로 유연하게 제어
- **Unity 실전 팁**: SRP로 파이프라인 커스터마이즈, Render Feature로 후처리/특수효과 추가
- **DirectX 실전 팁**: Input Layout/Shader Stage/Output Merger 직접 제어, DXR로 레이트레이싱 파이프라인 구현
- **현업 사례**: AAA 게임은 커스텀 파이프라인, 모바일은 경량화, 영화는 오프라인 파이프라인
- **Unity vs DirectX**: Unity는 고수준 자동화, DirectX는 저수준 커스텀/최적화 강점

## 예상 면접 질문과 답변
- Q. 그래픽스 파이프라인의 주요 단계와 각 역할은?
  A. 입력(정점/속성), 변환, 래스터화, 픽셀, 출력 등.
- Q. 고정 파이프라인과 프로그래머블 파이프라인의 차이는?
  A. 고정은 하드웨어 내장, 프로그래머블은 셰이더로 유연하게 제어.
- Q. Unity에서 SRP의 장점은?
  A. 렌더링 파이프라인을 자유롭게 커스터마이즈 가능.
- Q. DirectX에서 파이프라인 최적화 방법은?
  A. 드로우콜 최소화, 셰이더 최적화, 배칭 등.
- Q. 래스터화와 레이트레이싱의 차이는?
  A. 래스터화는 2D 변환, 레이트레이싱은 광선 추적 기반.
