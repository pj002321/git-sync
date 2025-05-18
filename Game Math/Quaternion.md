
## 사원수 (QUATERNION)

#### What is Quaternion

- 정의 (Definition):
	- 사원수(Quaternion)는 3D 회전을 표현하는 4차원 수학적 구조로, (x, y, z, w)로 구성된다.
	- 짐벌락(Gimbal Lock) 문제 없이 부드러운 회전, 보간(Slerp) 등에 강점.
	- 게임 엔진에서 3D 오브젝트의 회전, 카메라 제어 등에 널리 사용.

- 예시 (Examples):
	- Unity에서 Quaternion.Euler(0, 90, 0)로 90도 회전 생성.
	- 두 회전의 Slerp(구면 선형 보간):
```csharp
Quaternion q = Quaternion.Slerp(q1, q2, t);
```
	- 쿼터니언 곱셈(회전 합성):
```csharp
Quaternion q3 = q1 * q2;
```

## 주제별 세부 내용 정리와 설명
- **사원수 수식**: q = w + xi + yj + zk, 단위 사원수(norm=1)로 회전 표현
- **오일러 각 vs 사원수**: 오일러는 짐벌락 발생, 사원수는 부드러운 연속 회전
- **Slerp**: 두 회전 사이를 일정 속도로 보간
- **Unity 실전 팁**: Transform.rotation, Quaternion.LookRotation, Slerp 등 활용
- **DirectX 실전 팁**: XMVECTOR, XMQuaternionSlerp 등 내장 함수 활용
- **현업 사례**: 3D 캐릭터 애니메이션, 카메라 트래킹, 비행/차량 시뮬레이션 등

## 예상 면접 질문과 답변
- Q. 사원수의 장점은?
  A. 짐벌락 없이 부드러운 3D 회전, 보간에 강점.
- Q. 오일러 각과 사원수의 차이점은?
  A. 오일러는 각 축별 회전, 사원수는 4D 벡터로 연속 회전.
- Q. Slerp란?
  A. 두 회전 사이를 일정 속도로 보간하는 방법.
- Q. Unity에서 사원수 회전 활용 예시는?
  A. Transform.rotation, LookRotation, Slerp 등.
- Q. DirectX에서 사원수 연산을 최적화하는 방법은?
  A. SIMD, 내장 함수(XMQuaternion*) 활용. 

[[GameMath]]
