
---
## 행렬 (MATRIX)

#### What is Matrix

- 정의 (Definition):
	- 행렬은 수치 데이터를 직사각형 배열로 표현한 수학적 구조로, 게임 수학에서 변환(이동, 회전, 스케일) 연산에 필수적이다.
	- 2D/3D 변환 행렬: 2x2, 3x3, 4x4 등 다양한 크기 사용.
	- 주요 연산: 곱셈(변환 합성), 역행렬(되돌리기), 전치(행/열 교환) 등.

- 예시 (Examples):
	- Unity에서 4x4 변환 행렬(Matrix4x4)로 월드/뷰/프로젝션 변환 구현.
	- 3D 회전 행렬 예시:
```csharp
Matrix4x4 rotY = Matrix4x4.Rotate(Quaternion.Euler(0, 90, 0));
```
	- 행렬 곱셈으로 변환 합성:
```csharp
Vector3 worldPos = matrix.MultiplyPoint(localPos);
```

## 주제별 세부 내용 정리와 설명
- **행렬 변환 종류**: 이동(Translation), 회전(Rotation), 스케일(Scale), 투영(Projection)
- **2D vs 3D**: 2D는 3x3, 3D는 4x4 행렬 주로 사용
- **행렬 곱셈 순서**: 변환 순서에 따라 결과 달라짐(Scale→Rotate→Translate 등)
- **Unity 실전 팁**: Transform 컴포넌트, Matrix4x4, Quaternion 등 활용
- **DirectX 실전 팁**: XMMATRIX, XMMatrixLookAtLH 등 내장 함수 활용
- **현업 사례**: 본(뼈대) 애니메이션, 카메라 변환, 물리 시뮬레이션 등

## 예상 면접 질문과 답변
- Q. 행렬 곱셈의 의미는?
  A. 여러 변환(이동, 회전, 스케일)을 하나로 합성.
- Q. 2D와 3D 행렬의 차이점은?
  A. 2D는 3x3, 3D는 4x4 행렬로 좌표 변환.
- Q. 행렬의 역행렬은 언제 필요한가?
  A. 변환을 되돌릴 때(예: 월드→로컬 변환).
- Q. Unity에서 행렬 변환을 어떻게 활용?
  A. Transform, Matrix4x4, Quaternion 등으로 위치/회전/스케일 제어.
- Q. DirectX에서 행렬 연산을 최적화하는 방법은?
  A. SIMD, 내장 함수(XMMatrix*) 활용. 


[[GameMath]]
