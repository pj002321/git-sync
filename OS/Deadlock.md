# Deadlock (교착 상태)

> [!NOTE] Deadlock
> 교착 상태는 **두 개 이상의 프로세스가 서로 필요로 하는 자원을 점유한 채, 다른 프로세스가 점유한 자원을 기다리느라 무한정 멈춰있는 상태**를 의미합니다. 마치 서로 다른 방향으로 가려는 두 차량이 좁은 길에서 서로 막혀 움직이지 못하는 상황과 같습니다.


# 🔳 4가지 필요 충분 조건
--------------------------------------------------------------------
1. 상호 배제 (Mutual Exclusion) : 특정 시간에 하나의 프로세스만 해당 자원을 사용할 수 있어야한다.
2. 점유 대기 (Hold and Wait) : 프로세스가 이미 하나 이상의 자원을 점유한 채, 다른 프로세스가 점유한 자원을 기다려야 한다.
3. 비 선점 (No Preemption) : 프로세스가 점유한 자원을 자발적으로 방출될 때까지 강제로 빼앗을 수 없다.
4. 순환 대기 (Circualr Wait) : 프로세스의 집합에서 P1 은 P2가 점유한 자원을 기다리고, P2는 P3가 점유한 자원을 기다리고  Pn은 P1이 점유한 자원을 기다리는 순환적인 형태의 대기 관계가 존재해야한다.

# 🔳 교착 상태 처리 방법
1. 예방 : 4가지 필요 충분 조건 중 하나 이상이 성립하지 않도록 시스템을 설계. (모든 자원을 한번에 요청, 자원 점유 중 다른 자원 요청 금지)
2. 회피 : 자원 할당 시 교착 상태 발생 가능성을 미리 파악하여 안전한 순서로만 자원 할당
   (은행원 알고리즘)
3. 탐지 : 시스템에 교착 상태가 발생했는지 주기적으로 확인. 발생 하면 복구 (자원 할당 그래프)
4. 무시 : 교착 상태 발생 빈도가 낮거나 복구 비용이 클 때는 무시(시스템 재부팅을 해버린다.)


## 📄 교착 상태란 무엇이고, 발생 조건 4가지 설명
--------------------------------------------------------------------
두 개 이상의 프로세스가 서로 필요한 자원을 점유하고 기다리느라 멈춰있는 상태입니다. 발생 조건은 상호 배제, 점유 대기, 비선점, 순환 대기입니다.

## 📄 교착 상태를 예방하는 방법의 예를 들어 설명
--------------------------------------------------------------------
모든 프로세스가 시작 전에 필요한 모든 자원을 한 번에 요청하도록 설계하여 점유 대기 조건을 방지할 수 있습니다.

## 📄 은행원 알고리즘은 교착 상태를 어떻게 회피하는가?
--------------------------------------------------------------------
시스템의 자원 할당 상태를 추적하며, 안전한 상태를 유지할 수 있는 범위 내에서만 자원을 할당합니다.

## 📄 교착 상태 탐지 후 복구하는 일반적인 방법은 무엇인가요?
--------------------------------------------------------------------
교착 상태에 있는 프로세스를 강제로 종료하거나, 점유한 자원을 선점하여 다른 프로세스에게 할당하는 방법 등이 있습니다.

## 📄 대부분의 운영체제에서 교착 상태를 무시하는 이유는 무엇인가요?
--------------------------------------------------------------------
교착 상태 발생 빈도가 낮고, 탐지 및 복구에 상당한 오버헤드가 발생할 수 있기 때문입니다. 시스템 재부팅이 더 간단하고 비용 효율적인 경우가 많습니다.

[[OS]]