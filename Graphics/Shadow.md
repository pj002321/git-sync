
# Shadow
# DirectX에서의 그림자 (Shadow) 생성 과정 상세 설명 🌒

3D 그래픽스에서 그림자는 장면에 사실감과 깊이감을 더하는 매우 중요한 요소입니다. 물체의 위치, 빛과의 관계를 시각적으로 명확하게 해주어 사용자가 공간을 더 잘 인지하도록 돕습니다. DirectX에서는 주로 **섀도우 맵핑(Shadow Mapping)** 기법을 기반으로 그림자를 생성합니다.

---

## 섀도우 맵핑 (Shadow Mapping)의 핵심 원리

섀도우 맵핑의 기본 아이디어는 "빛의 관점에서 씬(scene)을 바라봤을 때, 빛에 직접 닿는 가장 가까운 표면들의 깊이(거리) 정보를 저장하는 것"입니다. 이 깊이 정보가 담긴 텍스처를 **섀도우 맵(Shadow Map)**이라고 합니다.

1.  **빛의 시점에서 렌더링:**
    * 광원(Light Source)의 위치와 방향에서 씬을 렌더링합니다.
    * 이때, 일반적인 색상 정보 대신 각 픽셀에 해당하는 표면까지의 깊이 값(광원으로부터의 거리)을 텍스처(섀도우 맵)에 기록합니다.
2.  **카메라 시점에서 렌더링 (실제 화면 렌더링):**
    * 카메라의 시점에서 씬을 정상적으로 렌더링합니다.
    * 화면에 그려질 각 픽셀(프래그먼트)에 대해 다음을 수행합니다:
        * 해당 프래그먼트의 월드 좌표를 빛의 시점으로 변환합니다.
        * 변환된 좌표를 사용하여 섀도우 맵에서 해당 위치의 깊이 값(1단계에서 저장된 값)을 읽어옵니다.
        * 현재 프래그먼트의 실제 빛으로부터의 거리와 섀도우 맵에서 읽은 깊이 값을 비교합니다.
        * 만약 현재 프래그먼트의 빛으로부터의 거리가 섀도우 맵에 저장된 깊이 값보다 크다면, 해당 프래그먼트는 다른 물체에 의해 가려져 빛을 받지 못하는 **그림자 영역**에 있는 것입니다. 그렇지 않다면 빛을 받는 영역입니다.

---

## DirectX에서의 그림자 생성 과정 (섀도우 맵핑 상세)

섀도우 맵핑은 주로 두 개의 렌더링 패스(pass)로 나뉘어 처리됩니다.

### 렌더링 패스 1: 섀도우 맵 생성 (빛의 관점)

이 단계에서는 빛의 위치와 방향을 카메라로 간주하고 씬을 렌더링하여 섀도우 맵(깊이 텍스처)을 만듭니다.

1.  **렌더 타겟 설정:**
    * 컬러 버퍼 대신 **깊이 버퍼(Depth Buffer)로 사용될 텍스처**를 렌더 타겟으로 설정합니다. 이 텍스처가 바로 섀도우 맵이 됩니다. (`ID3D11DeviceContext::OMSetRenderTargets` 사용, 컬러 버퍼는 `NULL`로, 깊이 스텐실 뷰(`ID3D11DepthStencilView`)는 섀도우 맵용으로 생성된 뷰로 설정)
    * 일반적으로 이 텍스처는 부동 소수점 포맷(예: `DXGI_FORMAT_R32_TYPELESS`로 생성 후 `DXGI_FORMAT_D32_FLOAT`로 깊이 뷰, `DXGI_FORMAT_R32_FLOAT`로 셰이더 리소스 뷰 생성)을 사용합니다.

2.  **뷰 및 투영 행렬 설정 (빛 기준):**
    * **뷰 행렬 (Light's View Matrix):** 빛의 위치, 바라보는 방향, 업 벡터를 기준으로 뷰 행렬을 생성합니다. (예: `XMMatrixLookAtLH`)
    * **투영 행렬 (Light's Projection Matrix):** 빛의 종류에 따라 투영 행렬을 설정합니다.
        * **방향성 광원 (Directional Light):** 직교 투영(Orthographic Projection)을 사용합니다. (예: `XMMatrixOrthographicLH`) 빛의 영향 범위를 포함하는 육면체를 정의합니다.
        * **점 광원 (Point Light) / 스포트라이트 (Spot Light):** 원근 투영(Perspective Projection)을 사용합니다. (예: `XMMatrixPerspectiveFovLH`) 빛의 시야각(FOV)과 종횡비를 설정합니다.

3.  **정점 셰이더 (Vertex Shader - Shadow Map Pass):**
    * 입력된 모델 정점들을 **빛의 뷰-투영(View-Projection) 행렬**을 사용하여 변환합니다.
    * 주 목적은 정점의 깊이 값을 정확히 계산하는 것입니다.
    * HLSL 예시 (간략):
        ```hlsl
        cbuffer LightMatrixBuffer : register(b0)
        {
            matrix lightViewProjectionMatrix;
        };

        struct VS_INPUT
        {
            float4 position : POSITION;
        };

        struct VS_OUTPUT
        {
            float4 positionCS : SV_Position; // 클립 공간 위치
            // 특별한 추가 데이터는 보통 불필요
        };

        VS_OUTPUT main(VS_INPUT input)
        {
            VS_OUTPUT output;
            // 월드 변환은 이미 적용되었거나, 여기서 모델 * 빛의 뷰-투영 행렬을 적용
            output.positionCS = mul(input.position, lightViewProjectionMatrix);
            return output;
        }
        ```

4.  **픽셀 셰이더 (Pixel Shader - Shadow Map Pass):**
    * **가장 간단한 경우, 픽셀 셰이더가 필요 없을 수도 있습니다 (NULL 픽셀 셰이더).** GPU가 깊이 버퍼에 자동으로 깊이 값을 기록하기 때문입니다.
    * 만약 특정 연산(예: 깊이 값의 선형화 또는 사용자 정의 패킹)이 필요하다면 간단한 픽셀 셰이더를 사용합니다.
    * 컬러 값은 출력하지 않거나 무시됩니다.

5.  **래스터라이저 상태 설정:**
    * **뷰포트(Viewport):** 섀도우 맵의 해상도에 맞게 설정합니다.
    * **컬링 모드(Culling Mode):** 그림자 여드름(Shadow Acne) 현상을 줄이기 위해 `D3D11_CULL_FRONT` (앞면 컬링)을 사용하기도 합니다. (깊이 편향과 함께 사용)
    * **깊이 편향(Depth Bias):** 그림자 여드름을 완화하기 위해 매우 중요합니다. 래스터화 시 계산된 깊이 값에 약간의 편향을 더합니다. (`D3D11_RASTERIZER_DESC`의 `DepthBias`, `SlopeScaledDepthBias`, `DepthBiasClamp` 설정)

### 렌더링 패스 2: 최종 씬 렌더링 (카메라 관점)

이 단계에서는 카메라의 시점에서 씬을 렌더링하면서, 패스 1에서 생성된 섀도우 맵을 사용하여 각 픽셀의 그림자 여부를 판단합니다.

1.  **렌더 타겟 설정:**
    * 화면에 표시될 최종 이미지의 렌더 타겟(컬러 버퍼)과 깊이 버퍼를 설정합니다.

2.  **뷰 및 투영 행렬 설정 (카메라 기준):**
    * 카메라의 뷰 행렬과 투영 행렬을 정상적으로 설정합니다.

3.  **정점 셰이더 (Vertex Shader - Main Pass):**
    * 입력된 모델 정점들을 **카메라의 월드-뷰-투영(World-View-Projection) 행렬**을 사용하여 변환합니다 (일반적인 렌더링).
    * **추가적으로,** 정점의 월드 좌표를 **빛의 뷰-투영 행렬**로 변환하여 "빛의 시점에서의 클립 공간 좌표" (또는 텍스처 좌표로 변환된 형태)를 계산하고, 이를 픽셀 셰이더로 넘겨줍니다.
    * HLSL 예시 (간략):
        ```hlsl
        cbuffer CameraMatrixBuffer : register(b0)
        {
            matrix worldMatrix;
            matrix viewProjectionMatrix;
        };

        cbuffer LightMatrixBuffer : register(b1) // 패스 1에서 사용한 빛의 행렬
        {
            matrix lightViewProjectionMatrix;
        };

        struct VS_INPUT
        {
            float4 positionOS : POSITION; // 오브젝트 공간 위치
            // ... 기타 정점 데이터 (노멀, 텍스처 좌표 등)
        };

        struct PS_INPUT
        {
            float4 positionCS : SV_Position;    // 카메라 클립 공간 위치
            float4 shadowCoordPS : TEXCOORDN; // 빛 공간에서의 좌표 (픽셀 셰이더 입력용)
            // ... 기타 보간될 데이터
        };

        PS_INPUT main(VS_INPUT input)
        {
            PS_INPUT output;
            float4 worldPos = mul(input.positionOS, worldMatrix);
            output.positionCS = mul(worldPos, viewProjectionMatrix);
            output.shadowCoordPS = mul(worldPos, lightViewProjectionMatrix); // 빛 공간 좌표 계산
            // ...
            return output;
        }
        ```

4.  **픽셀 셰이더 (Pixel Shader - Main Pass):**
    * 정점 셰이더에서 보간된 `shadowCoordPS` (빛 공간 좌표)를 받습니다.
    * **원근 나누기 (Perspective Division):** `shadowCoordPS.xyz /= shadowCoordPS.w` 를 수행하여 NDC(Normalized Device Coordinates)로 변환합니다. (-1에서 1 범위 또는 0에서 1 범위)
    * **텍스처 좌표 변환:** NDC 좌표를 섀도우 맵 텍스처를 샘플링하기 위한 UV 좌표(0에서 1 범위)로 변환합니다. DirectX에서는 Y축을 반전하고, 범위 조정이 필요할 수 있습니다.
    * **섀도우 맵 샘플링:** 변환된 UV 좌표를 사용하여 섀도우 맵(`Texture2D shadowMap`으로 바인딩된 `ID3D11ShaderResourceView`)을 샘플링합니다. 이 값은 빛에서 가장 가까운 표면까지의 저장된 깊이(`storedDepthFromLight`)입니다.
    * **깊이 비교:**
        * 현재 프래그먼트의 빛으로부터의 깊이(`currentDepthFromLight`)는 `shadowCoordPS`의 변환된 z값 (예: `shadowTexCoord.z`) 입니다.
        * `currentDepthFromLight` 와 `storedDepthFromLight` 를 비교합니다.
        * **그림자 여부 판단:** `if (currentDepthFromLight > storedDepthFromLight + bias)` 이면 그림자 상태입니다. `bias`는 그림자 여드름을 피하기 위한 작은 값입니다.
    * **조명 계산:** 그림자 상태에 따라 최종 조명을 계산합니다. 그림자 안쪽이면 직접광을 제외하고 간접광(앰비언트)만 적용하거나, 그림자 계수(0.0 또는 부드러운 그림자의 경우 0.0 ~ 1.0 사이 값)를 곱합니다.
    * **PCF (Percentage Closer Filtering):** 하드웨어 지원(`SampleCmp` 또는 `SampleCmpLevelZero`) 또는 수동 샘플링을 통해 그림자 경계를 부드럽게 처리할 수 있습니다.
    * HLSL 예시 (간략, 하드웨어 PCF 사용):
        ```hlsl
        Texture2D shadowMap : register(t0);
        SamplerComparisonState shadowSampler : register(s0); // 비교 샘플러

        struct PS_INPUT
        {
            float4 positionCS : SV_Position;
            float4 shadowCoordPS : TEXCOORDN; // 빛 공간에서의 클립 공간 좌표
            // ...
        };

        float4 main(PS_INPUT input) : SV_Target
        {
            // 1. 원근 나누기
            float3 shadowCoordNDC = input.shadowCoordPS.xyz / input.shadowCoordPS.w;

            // 2. 텍스처 좌표로 변환
            float2 shadowTexCoord;
            shadowTexCoord.x = shadowCoordNDC.x * 0.5f + 0.5f;
            shadowTexCoord.y = shadowCoordNDC.y * -0.5f + 0.5f; // DirectX 텍스처 Y축

            float currentDepthFromLight = shadowCoordNDC.z; // 0~1 범위로 가정 (투영 행렬에 따라 다름)

            // 3. 섀도우 맵 샘플링 및 비교 (PCF)
            float shadowFactor = shadowMap.SampleCmpLevelZero(shadowSampler, shadowTexCoord, currentDepthFromLight);
            
            float3 finalColor = CalculateLighting(/*...*/) * shadowFactor + ambientColor;
            return float4(finalColor, 1.0f);
        }
        ```

5.  **셰이더 리소스 및 샘플러 설정:**
    * 패스 1에서 생성된 섀도우 맵(깊이 텍스처)을 픽셀 셰이더의 텍스처 리소스(`ID3D11ShaderResourceView`)로 바인딩합니다.
    * 섀도우 맵을 샘플링할 때 사용할 샘플러 상태(`ID3D11SamplerState`)를 설정합니다.
        * PCF를 사용하려면 비교 샘플러(`D3D11_FILTER_COMPARISON_MIN_MAG_LINEAR_MIP_POINT` 등, `D3D11_COMPARISON_FUNC` 설정)를 사용합니다.
        * 경계 처리(Address Mode)는 보통 `CLAMP` 또는 `BORDER` (경계 밖은 항상 빛을 받는 것으로 처리)를 사용합니다.

---

## 주요 문제점 및 개선 기법

* **그림자 여드름 (Shadow Acne / Surface Acne):**
    * **원인:** 섀도우 맵의 해상도 한계와 부동 소수점 정밀도 문제로 인해 물체가 자기 자신에게 그림자를 드리우는 것처럼 보이는 현상입니다.
    * **해결책:**
        * **깊이 편향 (Depth Bias):** 섀도우 맵을 생성하거나 샘플링할 때 깊이 값에 약간의 편향을 추가합니다. (DirectX 래스터라이저 상태의 `DepthBias`, `SlopeScaledDepthBias`)
        * **법선 편향 (Normal Offset):** 그림자 계산 시 표면 법선 방향으로 약간 떨어진 위치에서 계산합니다.

* **피터 패닝 (Peter Panning):**
    * **원인:** 깊이 편향을 과도하게 사용할 경우, 그림자가 물체로부터 분리되어 떠다니는 것처럼 보이는 현상입니다.
    * **해결책:** 깊이 편향 값을 적절히 조절해야 합니다. 슬로프 스케일 편향이 도움이 될 수 있습니다.

* **앨리어싱된 그림자 경계 (Aliased Shadow Edges):**
    * **원인:** 섀도우 맵의 해상도가 낮으면 그림자 경계가 각져 보입니다.
    * **해결책:**
        * **PCF (Percentage Closer Filtering):** 섀도우 맵에서 여러 점을 샘플링하여 결과를 평균내어 그림자 경계를 부드럽게 만듭니다. DirectX에서는 `SampleCmpLevelZero` (하드웨어 PCF)나 여러 번의 `Sample`을 통해 구현할 수 있습니다.
        * **CSM (Cascaded Shadow Maps):** 넓은 영역을 커버하는 방향성 광원(태양 등)의 경우, 카메라 시야 절두체를 여러 개의 작은 영역(cascade)으로 나누고 각 영역마다 별도의 고해상도 섀도우 맵을 생성합니다. 픽셀 셰이더는 해당 픽셀이 속한 cascade의 섀도우 맵을 샘플링합니다.
        * **VSM (Variance Shadow Maps), ESM (Exponential Shadow Maps):** 더 부드러운 그림자를 생성하는 고급 기법들이지만, 빛샘(light bleeding) 현상 등의 단점이 있을 수 있습니다.

---

DirectX에서 그림자를 구현하는 것은 다소 복잡할 수 있지만, 위에서 설명한 단계와 기법들을 이해하면 사실적인 3D 환경을 만드는 데 큰 도움이 될 것입니다. 각 프로젝트의 특성과 요구 사항에 맞춰 다양한 기법들을 조합하고 최적화하는 것이 중요합니다.

[[Graphics]]