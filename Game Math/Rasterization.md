
---
## 레스터화 (RASTERIZATION)

#### What is Rasterization

- 정의 (Definition):
	- 레스터화는 3D 모델의 기하 정보를 2D 화면의 픽셀로 변환하는 그래픽스 파이프라인의 핵심 과정이다.
	- 삼각형 등 폴리곤을 스캔라인/버리센트릭 좌표 등으로 픽셀에 할당.
	- 실시간 렌더링(게임, UI 등)에서 표준 방식.

- 예시 (Examples):
	- DirectX/Unity에서 삼각형을 화면에 그릴 때 내부 픽셀 판정:
```c
// Barycentric coordinates로 픽셀 내부 판정
float w0 = EdgeFunction(v1, v2, p);
float w1 = EdgeFunction(v2, v0, p);
float w2 = EdgeFunction(v0, v1, p);
if (w0 >= 0 && w1 >= 0 && w2 >= 0) { /* 픽셀 내부 */ }
```
	- Unity에서 MeshRenderer가 3D 모델을 2D 화면에 출력

## 주제별 세부 내용 정리와 설명
- **레스터화 알고리즘**: 스캔라인, 버리센트릭 좌표, Z-buffer(깊이 판정)
- **래스터화 vs 레이트레이싱**: 래스터화는 속도↑, 레이트레이싱은 품질↑
- **픽셀 셰이딩**: 픽셀별 색상/조명/텍스처 처리
- **Unity 실전 팁**: MeshRenderer, Camera, RenderTexture 등 활용
- **DirectX 실전 팁**: Pixel Shader, Depth/Stencil Buffer, Viewport 등 직접 제어
- **현업 사례**: 실시간 게임, UI, CAD 등

## 예상 면접 질문과 답변
- Q. 레스터화란?
  A. 3D 기하 정보를 2D 픽셀로 변환하는 과정.
- Q. 레스터화와 레이트레이싱의 차이는?
  A. 래스터화는 속도↑, 레이트레이싱은 품질↑.
- Q. 레스터화에서 픽셀 내부 판정 방법은?
  A. 버리센트릭 좌표, 스캔라인 등.
- Q. Unity에서 레스터화 관련 컴포넌트는?
  A. MeshRenderer, Camera, RenderTexture 등.
- Q. DirectX에서 레스터화 최적화 방법은?
  A. Z-buffer, Viewport, Pixel Shader 최적화 등. 



[[GameMath]]
