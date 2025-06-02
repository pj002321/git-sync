
# Mattrix

게임 개발에서 **행렬(Matrix)**은 단순히 숫자의 배열이 아니라, 3D 공간의 객체를 움직이고, 돌리고, 크기를 바꾸고, 카메라 시점을 조정하는 등 **그래픽스 처리의 핵심적인 역할**을 수행하는 매우 중요한 도구입니다. DirectX나 Unity와 같은 게임 엔진 및 그래픽스 API에서 행렬은 빼놓을 수 없는 요소이죠. 면접에서 자주 등장하는 주제이니만큼 확실하게 이해하고 넘어갑시다!

---

### 1. 행렬, 왜 게임에서 중요할까요? 🤔

쉽게 말해, 행렬은 **변환(Transformation)**을 표현하고 적용하는 가장 효율적인 방법입니다. 게임 속 캐릭터, 물체, 카메라 등 모든 것은 3D 공간 좌표를 가지고 있는데, 이 좌표들을 일관된 방식으로 변경(변환)하기 위해 행렬 연산을 사용합니다.

* **여러 변환의 조합 용이:** 이동, 회전, 크기 조절 등 여러 변환을 행렬 곱셈 한 번으로 합칠 수 있어 계산 효율성이 높습니다.
* **하드웨어 가속:** GPU는 행렬 연산에 최적화되어 있어 매우 빠른 속도로 그래픽 처리가 가능합니다.
* **표준화된 방식:** 대부분의 그래픽스 API (DirectX, OpenGL, Vulkan)와 게임 엔진 (Unity, Unreal Engine)이 표준적으로 행렬을 사용합니다.

---

### 2. 행렬의 기본과 핵심 연산: 변환의 시작 📐

주로 3D 그래픽스에서는 **4x4 행렬**을 사용합니다. 3차원 좌표(x, y, z)를 다루는데 왜 4x4 행렬을 사용할까요? 바로 **동차 좌표계(Homogeneous Coordinates)** 때문입니다. 동차 좌표계를 사용하면 이동(Translation) 변환도 다른 변환(회전, 크기 조절)과 마찬가지로 행렬 곱셈으로 한 번에 표현할 수 있게 됩니다. 3D 좌표 `(x, y, z)`는 동차 좌표계에서 `(x, y, z, 1)`로 표현됩니다. `w` 성분(마지막 값)은 보통 1로 설정합니다.

가장 기본적인 변환 행렬들은 다음과 같습니다.

* **이동 행렬 (Translation Matrix):** 물체를 특정 방향으로 ($t_x, t_y, t_z$)만큼 이동시킵니다.
    $$
    T = \begin{pmatrix} 1 & 0 & 0 & t_x \\ 0 & 1 & 0 & t_y \\ 0 & 0 & 1 & t_z \\ 0 & 0 & 0 & 1 \end{pmatrix}
    $$

* **크기 조절 행렬 (Scaling Matrix):** 물체의 크기를 각 축 방향으로 ($s_x, s_y, s_z$)배 만큼 조절합니다.
    $$
    S = \begin{pmatrix} s_x & 0 & 0 & 0 \\ 0 & s_y & 0 & 0 \\ 0 & 0 & s_z & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix}
    $$

* **회전 행렬 (Rotation Matrix):** 물체를 특정 축을 기준으로 회전시킵니다. 예를 들어, Z축 기준 $\theta$ 만큼 회전하는 행렬은 다음과 같습니다. (X축, Y축 회전 행렬도 유사한 형태를 가집니다.)
    $$
    R_z(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta & 0 & 0 \\ \sin\theta & \cos\theta & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix}
    $$

**행렬 곱셈의 순서가 매우 중요합니다!** 일반적으로 `크기 조절 -> 회전 -> 이동` 순으로 적용합니다. 즉, `최종 변환 행렬 = 이동 행렬 * 회전 행렬 * 크기 조절 행렬` (TRS 행렬) 순으로 곱해집니다. `좌표 * 크기 * 회전 * 이동` 순서로 계산된다고 생각하면 됩니다. (API나 관례에 따라 순서는 달라질 수 있습니다.)

---

### 3. 그래픽스 변환 파이프라인과 행렬의 여정 🚀

3D 모델의 정점(Vertex) 데이터가 화면에 그려지기까지 여러 단계의 좌표계 변환을 거치게 되며, 각 단계마다 행렬이 사용됩니다. 이 과정을 **그래픽스 변환 파이프라인**이라고 합니다.

1.  **로컬 공간 (Local Space / Object Space) -> 월드 공간 (World Space)**
    * **모델 변환 (Model Transformation) / 월드 변환 (World Transformation)**: 모델 자체의 원점(피벗)을 기준으로 정의된 로컬 좌표를 게임 세계의 원점을 기준으로 하는 월드 좌표로 변환합니다. 각 물체는 자신만의 모델 행렬(또는 월드 행렬)을 가집니다.
    * `월드 좌표 = 월드 행렬 * 로컬 좌표`
    * 이 월드 행렬은 앞에서 설명한 이동, 회전, 크기 조절 행렬들의 조합으로 만들어집니다. ($M_{world} = T \cdot R \cdot S$)

2.  **월드 공간 (World Space) -> 뷰 공간 (View Space / Camera Space)**
    * **뷰 변환 (View Transformation)**: 월드 공간의 물체들을 카메라의 시점으로 변환합니다. 즉, 카메라를 월드 공간의 원점으로 가져오고, 카메라가 특정 방향을 바라보도록 월드 전체를 회전시키는 것과 같습니다.
    * `뷰 좌표 = 뷰 행렬 * 월드 좌표`
    * 뷰 행렬은 카메라의 위치(eye), 바라보는 지점(target/at), 그리고 카메라의 위쪽 방향(up vector)을 이용해 생성됩니다.

3.  **뷰 공간 (View Space) -> 클립 공간 (Clip Space / Homogeneous Clip Space)**
    * **투영 변환 (Projection Transformation)**: 3D 뷰 공간의 물체들을 2D 화면에 표시하기 위해 원근감이나 직교 투영을 적용합니다. 이 변환 결과로 정점들은 정규화된 육면체 공간(Normalized Device Coordinates, NDC로 가기 전 단계)으로 옮겨집니다.
    * `클립 좌표 = 투영 행렬 * 뷰 좌표`
    * **원근 투영 (Perspective Projection):** 가까이 있는 물체는 크게, 멀리 있는 물체는 작게 보이도록 합니다. 시야각(Field of View, FOV), 종횡비(Aspect Ratio), 근평면(Near Plane), 원평면(Far Plane) 등의 파라미터로 절두체(Frustum)를 정의하고, 이 절두체 안의 공간을 [-1, 1] 범위의 정규화된 공간으로 매핑합니다.
    * **직교 투영 (Orthographic Projection):** 물체의 거리에 관계없이 같은 크기로 보이도록 합니다. 주로 2D 게임이나 CAD 프로그램, 게임의 UI 등에 사용됩니다.

4.  **클립 공간 (Clip Space) -> 정규화된 장치 좌표 (Normalized Device Coordinates, NDC)**
    * **원근 나누기 (Perspective Division):** 클립 좌표의 각 성분(x, y, z)을 w 성분으로 나눕니다. 이를 통해 원근 효과가 적용되고, 좌표는 보통 -1에서 1 사이의 값으로 정규화됩니다. (DirectX의 경우 z는 0에서 1 사이)
    * `NDC 좌표 = (클립좌표.x / 클립좌표.w, 클립좌표.y / 클립좌표.w, 클립좌표.z / 클립좌표.w)`

5.  **정규화된 장치 좌표 (NDC) -> 화면 공간 (Screen Space)**
    * **뷰포트 변환 (Viewport Transformation):** NDC 좌표를 실제 모니터나 윈도우의 픽셀 좌표로 변환합니다. 화면의 해상도와 뷰포트 설정을 사용합니다.
    * `화면 좌표 = 뷰포트 행렬 * NDC 좌표`

결과적으로, 한 정점의 로컬 좌표 `P_local`이 화면에 그려지기까지의 전체 변환은 다음과 같은 행렬 곱으로 표현될 수 있습니다:

$P_{screen} = M_{viewport} \cdot (\text{Perspective Division}) \cdot M_{projection} \cdot M_{view} \cdot M_{world} \cdot P_{local}$

보통 정점 셰이더에서는 로컬 좌표를 클립 공간까지 변환하는 **MVP 행렬 (Model-View-Projection Matrix)**을 미리 계산하여 넘겨줍니다.

$MVP = M_{projection} \cdot M_{view} \cdot M_{world}$
$P_{clip} = MVP \cdot P_{local}$

---

### 4. DirectX와 Unity에서의 행렬 사용 💻

* **DirectX (C++ 기반):**
    * DirectXMath 라이브러리에서 `XMMATRIX` 와 같은 타입을 사용하여 행렬을 다룹니다.
    * `XMMatrixTranslation()`, `XMMatrixRotationX()`, `XMMatrixScaling()`, `XMMatrixLookAtLH()` (뷰 행렬), `XMMatrixPerspectiveFovLH()` (원근 투영 행렬) 등의 함수를 제공합니다. (LH는 왼손 좌표계를 의미)
    * 셰이더(HLSL)에서는 `float4x4` 타입으로 행렬을 선언하고, 상수 버퍼(Constant Buffer)를 통해 C++ 코드에서 계산된 행렬 값을 전달받아 정점 변환 등에 사용합니다.
    * 일반적으로 **행 우선(Row-Major) 방식**으로 행렬을 메모리에 저장하지만, 셰이더로 전달할 때는 열 우선(Column-Major)으로 변환해야 하는 경우가 많습니다 (셰이더 컴파일러 옵션이나 코드 내에서 전치(transpose)를 통해 처리).

* **Unity (C# 기반):**
    * `UnityEngine.Matrix4x4` 구조체를 사용합니다.
    * `Matrix4x4.Translate()`, `Matrix4x4.Rotate()`, `Matrix4x4.Scale()`, `Matrix4x4.TRS()` (이동, 회전, 크기를 한 번에) 등의 정적 메소드와 멤버 변수/함수를 제공합니다.
    * 카메라(Camera) 컴포넌트가 내부적으로 뷰 행렬(`camera.worldToCameraMatrix`)과 투영 행렬(`camera.projectionMatrix`)을 계산해줍니다.
    * 오브젝트의 `Transform` 컴포넌트는 로컬-월드 변환 행렬(`transform.localToWorldMatrix`)과 월드-로컬 변환 행렬(`transform.worldToLocalMatrix`)을 제공합니다.
    * 셰이더(ShaderLab/HLSL/Cg)에서는 `float4x4` 또는 `unity_ObjectToWorld` (모델 행렬), `UNITY_MATRIX_V` (뷰 행렬), `UNITY_MATRIX_P` (투영 행렬), `UNITY_MATRIX_VP` (뷰-투영 행렬), `UNITY_MATRIX_MVP` (모델-뷰-투영 행렬) 와 같은 내장 변수를 사용합니다.
    * Unity는 **열 우선(Column-Major) 방식**으로 행렬을 메모리에 저장하고 셰이더에 전달합니다. 또한, **오른손 좌표계**를 주로 사용합니다.

---

### 5. 면접 시 추가적으로 어필할 수 있는 포인트! 💡

* **좌표계의 차이:** DirectX는 주로 **왼손 좌표계(Left-Handed Coordinate System)**를 사용하고, OpenGL과 Unity는 주로 **오른손 좌표계(Right-Handed Coordinate System)**를 사용합니다. 이 차이로 인해 뷰 행렬이나 투영 행렬의 형태가 조금씩 다를 수 있습니다. 면접관이 특정 API를 언급하면 해당 API의 좌표계를 알고 있다고 어필하는 것이 좋습니다.
* **행 우선 vs 열 우선 (Row-Major vs Column-Major):** 행렬을 메모리에 저장하는 방식의 차이입니다. C/C++의 2차원 배열은 기본적으로 행 우선 방식이지만, 셰이더 언어(HLSL, GLSL)는 기본적으로 열 우선으로 행렬을 취급하는 경우가 많습니다. 데이터를 CPU에서 GPU로 전달할 때 이 차이를 인지하고 필요시 전치(Transpose) 연산을 해줘야 합니다.
* **쿼터니언 (Quaternion):** 회전을 표현할 때 행렬 대신 쿼터니언을 사용하기도 합니다. 쿼터니언은 짐벌락(Gimbal Lock) 현상을 피할 수 있고, 회전 간의 보간(interpolation)이 더 자연스럽다는 장점이 있습니다. 하지만 최종적으로 정점 변환에는 행렬이 사용되므로, 쿼터니언으로 계산된 회전도 결국 행렬로 변환되어 적용됩니다.
* **최적화:** 행렬 곱셈은 연산량이 많으므로, 불필요한 계산을 줄이는 것이 중요합니다. 예를 들어, 정적인 물체의 월드 행렬이나 카메라의 뷰/투영 행렬은 매 프레임 계산할 필요 없이 변경될 때만 업데이트하는 것이 좋습니다.

---

[[GameMath]]
