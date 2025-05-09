# Process

> [!NOTE] process
> 실행 중인 하나의 프로그램. 운영체제로부터 자원을 할당받아 독립적인 실행 환경을 가지는 작업의 단위. 하나의 독립된 일이다.

🔳 특징
- 독립적인 메모리 공간 : 자신만의 주소 공간을 가지므로 다른 프로세스의 메모리에 직접 접근할 수 없다.
- 최소 하나의 스레드 포함 : 프로세스가 실행되면 기본적으로 메인 스레드를 포함한다.
- 운영체제로부터 자원 할당 : CPU 시간, 메모리 공간, 파일, 장치 등을 할당받는다.
- 프로세스 간 통신 (IPC) : 파이프, 소켓, 공유 메모리 등 별도의 매커니즘을 통해 다른 프로세스와 데이터를 주고받을 수 있다. 


# Thread

> [!NOTE] thread
> 하나의 프로세스 내에서 실제로 작업을 수행하는 실행의 흐름이다.
> 프로세스 내에서 여러 개의 스레드가 동시에 실행될 수 있다. 마치 하나의 일을 처리하기 위해서 여러 명의 작업자의 역할이라고 생각할 수 있다.

🔳 특징
- 프로세스 자원 공유 : 같은 프로세스 내의 스레드들은 메모리, 파일, 코드 등의 자원을 공유한다.
- 독립적인 실행 흐름 : 각 스레드는 자신만의 프로그램 카운터 (PC) , 스택을 가지고 독립적으로 실행된다.
- 경량화 된 실행 단위 : 프로세스에 비해 생성 및 Context Switching 비용이 저렴하다.

프로세스는 하나 이상의 작업을 처리하기 위해 하나 이상의 실행 흐름(스레드)을 가질 수 있다.

[[OS]]
