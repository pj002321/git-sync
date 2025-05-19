

## 충돌검사 연산 (COLLISION DETECTION)

#### What is Collision Detection

- 정의 (Definition):
	- 충돌검사는 두 오브젝트가 겹치는지(교차, 접촉) 판정하는 연산으로, 게임 물리/그래픽스의 핵심.
	- AABB(축 정렬 박스), OBB(임의 박스), Sphere(구), Mesh(삼각형 집합) 등 다양한 방식 존재.
	- 실시간 게임에서 성능/정확도 균형이 중요.

- 예시 (Examples):
	- Unity에서 Collider/Physics.Raycast로 충돌 판정:
```csharp
if (Physics.Raycast(origin, dir, out hit, dist)) { /* 충돌 */ }
```
	- AABB 충돌 판정 코드:
```csharp
bool IntersectAABB(AABB a, AABB b) {
  return (a.max.x > b.min.x && a.min.x < b.max.x &&
          a.max.y > b.min.y && a.min.y < b.max.y &&
          a.max.z > b.min.z && a.min.z < b.max.z);
}
```

## 주제별 세부 내용 정리와 설명
- **AABB/OBB/Sphere/Mesh**: 단순(빠름)~정밀(느림) 충돌 방식
- **브로드/내로우 페이즈**: 전체 후보 좁히기(브로드), 실제 충돌 판정(내로우)
- **Unity 실전 팁**: Collider, Rigidbody, Physics.Raycast, LayerMask 등 활용
- **DirectX 실전 팁**: BoundingBox, BoundingSphere, Intersect 함수 등
- **현업 사례**: 캐릭터/총알/환경 충돌, 피직스 엔진, 최적화(Spatial Partitioning 등)

## 예상 면접 질문과 답변
- Q. AABB와 OBB의 차이는?
  A. AABB는 축 정렬, OBB는 임의 방향 박스(정확도↑, 연산량↑).
- Q. 브로드/내로우 페이즈란?
  A. 브로드는 후보 좁히기, 내로우는 실제 충돌 판정.
- Q. Unity에서 충돌검사 활용 예시는?
  A. Collider, Physics.Raycast, LayerMask 등.
- Q. DirectX에서 충돌검사 구현 방법은?
  A. BoundingBox, Intersect 등 내장 함수 활용.
- Q. 실무에서 충돌검사 최적화 방법은?
  A. Spatial Partitioning, LOD, 단순화된 히트박스 등. 

[[GameMath]]