
---
## 폴리곤 메쉬 (POLYGON MESH)

#### What is Polygon Mesh

- 정의 (Definition):
	- 폴리곤 메쉬는 정점(Vertex), 에지(Edge), 면(Face)으로 구성된 3D 모델의 기본 데이터 구조다.
	- 주로 삼각형(Tris), 사각형(Quads) 등 다각형 면의 집합으로 표현.
	- 게임 엔진에서 3D 오브젝트의 형태, 충돌, 렌더링 등에 사용.

- 예시 (Examples):
	- Unity에서 MeshFilter/MeshRenderer로 3D 모델(메쉬) 렌더링.
	- DirectX에서 정점/인덱스 버퍼로 메쉬 데이터 관리.
	- 삼각형 메쉬 생성 코드 예시:
```csharp
Mesh mesh = new Mesh();
mesh.vertices = new Vector3[] { v0, v1, v2 };
mesh.triangles = new int[] { 0, 1, 2 };
```

## 주제별 세부 내용 정리와 설명
- **정점/에지/면**: 정점(Vertex)은 위치, 에지(Edge)는 연결, 면(Face)은 폴리곤(삼각형/사각형 등)
- **삼각형 vs 사각형**: 삼각형은 모든 3D 엔진에서 지원, 사각형은 변환 시 삼각형으로 분할
- **메쉬 최적화**: LOD(Level of Detail), 노멀/UV/탠젠트 등 속성 추가, 버텍스 버퍼/인덱스 버퍼 활용
- **Unity 실전 팁**: MeshCollider, SkinnedMeshRenderer, SubMesh 등 활용
- **DirectX 실전 팁**: VertexBuffer, IndexBuffer, InputLayout 등 직접 제어
- **현업 사례**: 캐릭터/배경 모델링, 충돌 검사, 애니메이션 스키닝 등

## 예상 면접 질문과 답변
- Q. 폴리곤 메쉬의 구성 요소는?
  A. 정점(Vertex), 에지(Edge), 면(Face)로 구성.
- Q. 삼각형 메쉬가 표준인 이유는?
  A. 모든 평면 다각형을 삼각형으로 분할 가능, GPU/엔진 호환성 높음.
- Q. 메쉬 최적화 방법은?
  A. LOD, 버텍스/인덱스 버퍼, 속성 최소화 등.
- Q. Unity에서 메쉬 생성/활용 예시는?
  A. MeshFilter, MeshRenderer, MeshCollider 등.
- Q. DirectX에서 메쉬 데이터를 관리하는 방법은?
  A. VertexBuffer, IndexBuffer, InputLayout 등 활용. 

[[GameMath]]