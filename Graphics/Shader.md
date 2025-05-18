
## 셰이더 (SHADER)

#### What is Shader

- 정의 (Definition):
	- 셰이더는 GPU에서 실행되어 그래픽스 파이프라인의 각 단계를 제어하는 작은 프로그램이다.
	- 주요 종류: 버텍스(Vertex), 픽셀/프래그먼트(Pixel/Fragment), 지오메트리(Geometry), 컴퓨트(Compute) 셰이더 등.
	- 실시간 효과(조명, 그림자, 반사, PBR 등)와 오프라인 고품질 효과 모두 구현 가능.

- 예시 (Examples):
	- Unity ShaderLab으로 표면 셰이더 작성:
```csharp
Shader "Custom/SimpleDiffuse" {
  Properties { _Color ("Color", Color) = (1,1,1,1) }
  SubShader {
    Pass {
      CGPROGRAM
      #pragma vertex vert
      #pragma fragment frag
      fixed4 frag() : SV_Target { return _Color; }
      ENDCG
    }
  }
}
```
	- DirectX HLSL로 Lambert 조명 구현:
```hlsl
float NdotL = max(dot(normal, lightDir), 0);
float3 diffuse = NdotL * lightColor * materialColor;
```

## Literature Review

#### Akenine-Möller et al., 2018
- [Real-Time Rendering, Fourth Edition](https://www.crcpress.com/Real-Time-Rendering-Fourth-Edition/Akenine-Moller-Haines-Hoffman/p/book/9781138627000)
	- Source: CRC Press
- 주요 내용 (Key points):
	- 셰이더의 종류와 역할
	- 실시간 렌더링에서의 활용
	- 최적화 및 고급 효과 구현

#### Unity Technologies, 2020
- [Unity Manual: Shaders](https://docs.unity3d.com/kr/2020.3/Manual/Shaders.html)
	- Source: Unity Documentation
- 주요 내용 (Key points):
	- Unity에서의 셰이더 작성 방식
	- Shader Graph, HLSL, ShaderLab 등
	- 커스터마이즈와 최적화

## 주제별 세부 내용 정리와 설명
- **셰이더 종류**: Vertex(정점 변환), Pixel(색상/조명), Geometry(기하 변형), Compute(GPGPU)
- **ShaderLab vs HLSL**: ShaderLab은 Unity 고수준, HLSL은 DirectX/Unity 저수준 셰이더 언어
- **실시간 vs 오프라인**: 실시간은 최적화/속도, 오프라인은 품질/복잡 효과
- **Unity 실전 팁**: Shader Graph로 시각적 셰이더 설계, SRP에서 커스텀 셰이더 활용
- **DirectX 실전 팁**: HLSL로 직접 셰이더 작성, 분기 최소화/리소스 효율화로 성능 확보
- **현업 사례**: AAA 게임은 PBR/포스트 프로세싱 셰이더, 모바일은 경량화/최적화 셰이더

## 예상 면접 질문과 답변
- Q. 버텍스 셰이더와 픽셀 셰이더의 차이는?
  A. 버텍스는 정점 변환, 픽셀은 픽셀별 색상/조명 처리.
- Q. Unity에서 Shader Graph의 장점은?
  A. 시각적으로 셰이더를 설계, 복잡한 효과도 쉽게 구현.
- Q. DirectX에서 셰이더 최적화 방법은?
  A. 불필요한 연산 제거, 분기 최소화, 리소스 효율적 사용.
- Q. 머티리얼과 셰이더의 관계는?
  A. 머티리얼은 셰이더와 속성값을 조합한 렌더링 단위.
- Q. 실시간 렌더링에서 셰이더가 중요한 이유는?
  A. 다양한 시각 효과와 성능 최적화에 핵심 역할. 