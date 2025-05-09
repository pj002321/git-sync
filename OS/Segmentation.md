# Segmentation
--- 
운영체제의 메모리 관리 기법 중 하나로, 프로세스의 논리 주소 공간을 크기가 **가변적인 논리적 단위**인 세그먼트들로 나누어 관리한다.

>[!SEGMENTATION]
>각 세그먼트는 프로그램의 논리적인 부분(코드, 데이터, 스택, 서브루틴 등)을 나타낸다.
>물리 메모리는 고정된 크기로 나누어지지 않고, 세그먼트 크기에 맞춰 비어 있는 공간에 적재된다.
>- 세그먼트 테이블을 사용하여 각 세그먼트의 물리 메모리 시작 주소(Base)와 크기(Limit)정보를 저장한다.
>- CPU가 논리 주소 (세그먼트 번호, 세그먼트 내 오프셋)를 생성하면, 세그먼트 테이블을 통해 해당 물리 주소를 찾는다. 이때 오프셋이 세그먼트 크기를 넘는지 경계 검사를 수행한다.
>- 프로그래머에게 친숙한 논리적인 메모리 뷰를 제공하며, 세그먼트 단위로 공유나 보호가 용이하다.
>- 내부 단편화는 발생하지 않거나 적지만, 가변적인 크기로 인해 외부 단편화 문제가 발생할 수 있다.
>- 메모리 할당 및 회수 과정이 페이징 보다 복잡할 수 있다.


**📄Segmentation이 무엇인가요? Paiging과의 큰 차이는 무엇인가요?**
Segmentation은 프로세스의 논리 주소 공간을 코드, 데이터 등 가변 크기의 논리적 단위인 세그먼트로 나누어 관리하는 기법입니다. Paging과의 가장 큰 차이는 Paging은 고정 크기의 페이지/프레임을 사용하는 반면, Segmentation은 프로그램의 논리적 구조에 따른 가변 크기의 세그먼트를 사용한다는 점입니다.

**📄Segmentation에서 주소 변환 과정은 어떻게 되나요?**
CPU가 논리 주소 (세그먼트 번호, 세그먼트 내 오프셋)를 생성하면, 운영체제는 세그먼트 테이블에서 해당 세그먼트 번호의 물리적 시작 주소(Base)와 크기(Limit) 정보를 얻습니다. 오프셋이 Limit보다 작거나 같은지 검사한 후(경계 검사), 물리 주소는 Base + Offset으로 계산됩니다.

**📄Segmentation의 장점과 단점을 설명해주세요**
장점은 프로그램의 논리적 구조를 반영하여 메모리 관리가 용이하고, 세그먼트 단위 공유 및 보호가 편리하며, 내부 단편화가 발생하지 않는다는 점입니다. 단점은 가변 크기로 인해 물리 메모리에 외부 단편화가 발생할 수 있고, 메모리 할당 및 회수가 더 복잡하다는 점입니다.

**📄Segmentation과 Paging을 함께 사용할 수도 있나요?**
네, Segmentation과 Paging을 결합한 방식인 Segmented Paging을 사용할 수 있습니다. 이는 논리적인 세그먼트로 나눈 후, 각 세그먼트를 다시 고정 크기의 페이지 단위로 나누어 관리하는 방식입니다. 이를 통해 논리적인 구조를 유지하면서도 외부 단편화 문제를 해결할 수 있습니다.

[[OS]]