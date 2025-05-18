---
tags:
- unity-shader-lit-unlit-graphics
- unity-graphics-material-surface-shader
- 게임개발-면접-렌더링-머티리얼
aliases:
- UnityShader
- LitShader
- UnlitShader

## Unity 셰이더 (Unity Shader: Lit, Unlit 등)

#### What is Unity Shader (Lit, Unlit)

- 정의 (Definition):
    - Unity에서 셰이더는 머티리얼의 시각적 효과를 결정하는 GPU 프로그램입니다.
    - Lit 셰이더는 조명, 그림자, 반사 등 물리 기반(PBR) 조명 효과를 지원합니다.
    - Unlit 셰이더는 조명 영향을 받지 않고, 단순히 색상/텍스처만 출력합니다.
    - ShaderLab(HLSL 기반)으로 작성하거나, Shader Graph로 시각적으로 설계할 수 있습니다.

- 예시 (Examples):
    - Lit 머티리얼: PBR 조명, 반사, 노멀맵, 메탈릭 등 지원
    - Unlit 머티리얼: UI, HUD, 2D Sprite, 특수효과 등 조명 무시
    - Shader Graph로 커스텀 셰이더 제작
    - 코드 예시 (Unlit Shader):
```csharp
Shader "Custom/UnlitColor" {
  Properties { _Color ("Color", Color) = (1,1,1,1) }
  SubShader {
    Tags { "RenderType"="Opaque" }
    Pass {
      CGPROGRAM
      #pragma vertex vert
      #pragma fragment frag
      fixed4 _Color;
      fixed4 frag() : SV_Target { return _Color; }
      ENDCG
    }
  }
}
```
    - 코드 예시 (Lit Shader):
```csharp
Shader "Custom/LitSimple" {
  Properties { _MainTex ("Texture", 2D) = "white" {} }
  SubShader {
    Tags { "RenderType"="Opaque" }
    LOD 200
    CGPROGRAM
    #pragma surface surf Standard fullforwardshadows
    sampler2D _MainTex;
    struct Input { float2 uv_MainTex; };
    void surf(Input IN, inout SurfaceOutputStandard o) {
      o.Albedo = tex2D(_MainTex, IN.uv_MainTex).rgb;
    }
    ENDCG
  }
}
```

## Literature Review

#### Unity Technologies, 2024
- [Unity Manual: Shaders](https://docs.unity3d.com/kr/2022.3/Manual/Shaders.html)
    - Unity 셰이더 구조, ShaderLab, HLSL, Shader Graph, SRP 지원
- [Unity Manual: Lit Shader](https://docs.unity3d.com/kr/2022.3/Manual/shader-lit.html)
    - Lit 셰이더의 PBR, 머티리얼 속성, 조명/반사/노멀맵 등
- [Unity Manual: Unlit Shader](https://docs.unity3d.com/kr/2022.3/Manual/shader-unlit.html)
    - Unlit 셰이더의 특징, 활용 예시

#### Akenine-Möller et al., 2018
- [Real-Time Rendering, Fourth Edition](https://www.crcpress.com/Real-Time-Rendering-Fourth-Edition/Akenine-Moller-Haines-Hoffman/p/book/9781138627000)
    - 실시간 셰이더의 원리, PBR, 최적화, 다양한 셰이더 유형

## 주제별 세부 내용 정리와 설명
- **Lit Shader**: PBR 기반, 조명/그림자/반사/노멀맵/메탈릭 등 지원. 현실감 있는 3D 오브젝트에 사용.
- **Unlit Shader**: 조명 무시, 단순 색상/텍스처 출력. UI, 2D, 특수효과, HUD 등에 적합.
- **Shader Graph**: 노드 기반 시각적 셰이더 제작. 복잡한 효과도 코딩 없이 구현 가능.
- **Surface Shader**: Unity 고수준 셰이더. PBR, 조명, 그림자 등 자동 처리.
- **Custom HLSL**: 저수준 제어, 최적화/특수효과에 적합.
- **SRP(URP/HDRP)**: 파이프라인별 셰이더 구조/기능 다름. Lit/Unlit도 파이프라인에 따라 다르게 동작.
- **머티리얼과 셰이더**: 머티리얼은 셰이더+속성값 조합. 하나의 셰이더로 다양한 머티리얼 생성 가능.
- **실전 팁**: Lit은 PBR, Unlit은 UI/특수효과, Shader Graph는 프로토타이핑/비주얼 이펙트에 강점.

## Unity vs DirectX/Other Engines
- Unity: ShaderLab, Surface Shader, Shader Graph, HLSL 지원. 파이프라인별(Lit/Unlit) 표준 제공.
- DirectX: HLSL로 직접 셰이더 작성. 조명/머티리얼 직접 구현 필요.
- Unreal: Material Editor(노드 기반), HLSL/GLSL 지원. PBR 표준.

## 예상 면접 질문과 답변
- Q. Lit 셰이더와 Unlit 셰이더의 차이는?
  A. Lit은 조명/그림자/반사 등 PBR 효과 지원, Unlit은 조명 무시하고 색상/텍스처만 출력.
- Q. Unity에서 Unlit 셰이더는 언제 쓰나요?
  A. UI, HUD, 2D Sprite, 특수효과 등 조명 영향이 필요 없는 경우.
- Q. Lit 셰이더의 주요 속성은?
  A. Albedo, Metallic, Smoothness, Normal Map, Emission 등.
- Q. Shader Graph의 장점은?
  A. 시각적으로 셰이더를 설계, 복잡한 효과도 쉽게 구현.
- Q. Surface Shader와 HLSL 셰이더의 차이는?
  A. Surface Shader는 Unity가 조명/그림자 자동 처리, HLSL은 저수준 직접 제어.
- Q. SRP(URP/HDRP)에서 Lit/Unlit 셰이더의 차이는?
  A. 파이프라인별로 지원 속성/구조/최적화 방식이 다름.

## 관련 개념 (Related Concepts)
- [[머티리얼 (Material)]] #unity #material #shader
- [[렌더링 파이프라인 (Pipeline)]] #unity #pipeline #graphics
- [[Shader Graph]] #unity #shadergraph #visual
- [[조명 (Lighting)]] #unity #lighting #pbr 