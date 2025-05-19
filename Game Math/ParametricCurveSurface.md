
## 매개변수 곡선과 곡면 (PARAMETRIC CURVE & SURFACE)

#### What is Parametric Curve & Surface

- 정의 (Definition):
	- 매개변수 곡선은 t(매개변수)에 따라 점의 위치가 결정되는 곡선(예: 베지어, 스플라인 등)이다.
	- 매개변수 곡면은 (u, v) 두 매개변수로 3D 표면을 정의(예: NURBS, 패치 등).
	- 모델링, 애니메이션, 경로 생성 등 다양한 그래픽스/게임 분야에서 활용.

- 예시 (Examples):
	- 2차 베지어 곡선: B(t) = (1-t)^2 P0 + 2(1-t)t P1 + t^2 P2
	- Unity에서 Catmull-Rom 스플라인 경로 따라 이동:
```csharp
Vector3 pos = CatmullRom(p0, p1, p2, p3, t);
```
	- NURBS 곡면 생성(3D 모델링/CAD 등)

## 주제별 세부 내용 정리와 설명
- **베지어 곡선/곡면**: 제어점 기반, 간단한 곡선/곡면 생성
- **스플라인**: 여러 곡선을 부드럽게 연결, 경로/애니메이션에 활용
- **NURBS/패치**: 복잡한 곡면 모델링, CAD/3D 모델링에 필수
- **Unity 실전 팁**: LineRenderer, AnimationCurve, 경로 보간 등 활용
- **DirectX 실전 팁**: Tessellation, Patch, HLSL로 곡면 생성
- **현업 사례**: 자동차/캐릭터 경로, UI 애니메이션, 3D 모델링 등

## 예상 면접 질문과 답변
- Q. 베지어 곡선과 스플라인의 차이는?
  A. 베지어는 제어점 기반 단일 곡선, 스플라인은 여러 곡선 연결.
- Q. 매개변수 곡면이란?
  A. (u, v) 매개변수로 3D 표면을 정의하는 수학적 모델.
- Q. Unity에서 곡선/곡면 활용 예시는?
  A. AnimationCurve, LineRenderer, 경로 보간 등.
- Q. DirectX에서 곡면을 생성하는 방법은?
  A. Tessellation, Patch, HLSL 등 활용.
- Q. 실무에서 곡선/곡면이 중요한 이유는?
  A. 자연스러운 경로, 부드러운 모델링/애니메이션 구현. 

[[GameMath]]