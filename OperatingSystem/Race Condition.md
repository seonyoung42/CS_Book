# Race Condition(=경쟁 상태)

> 공유 자원에 여러 프로세스가 동시에 접근할 때 결과 값에 영향을 줄 수 있는 상태

여러 프로세스가 동시에 접근할 때 자료의 일관성을 해치는 결과가 나타나는 상태이다. 

예를 들어, 잔고가 100만원 있을 때 동시에 50만원과 70만원을 송금하려고 하는 경우 두 이체가 모두 성공하면 은행에 문제가 발생하는 상태

<br>

## Race Condition 발생 예시

#### 커널 작업 수행하는 중에 인터럽트 발생한 경우

> 커널 모드에서 데이터로 작업을 수행하다가 인터럽트가 발생하여 같은 데이터를 조작하게 되면 서로 다른 프로세스가 커널을 공유하게되어 Race condition 발생
    
- 해결 방법 : 커널 모드에서 작업을 수행하는 동안 인터럽트를 disable 시킴

<br>
   
#### 프로세스가 'System Call'을 하여 커널 모드로 진입하여 작업을 수행하는 도중 Context Switching이 발생한 경우
    
> 프로세스 1이 커널모드에서 데이터 작업을 하는 도중 시간이 초과되어 프로세스 2가 CPU를 점유하여 데이터를 조작하는 경우
    
- 해결 방법 : 프로세스가 커널모드에서 작업을 하는 경우 시간이 초과되어도 CPU 제어권이 다른 프로세스에게 넘어가지 않도록 한다.

<br>

#### 멀티 프로세서 환경에서 공유 메모리 내의 커널 데이터에 접근하는 경우
    
> 멀티 프로세서 환경에서 2개의 CPU가 동시에 커널 내부의 공유 데이터에 접근하여 조작하는 경우
    
- 해결 방법 : 커널 내부에 있는 각 공유 데이터에 접근할 때마다 해당 데이터에 대한 lock/unlock을 수행하게 함 → 매 순간 그 데이터에 접근하는 프로세스는 1개가 됨



<br>



## Race Condition 해결 조건

#### Mutual Exclusion (상호 배제)

  > 어떤 프로세스가 임계 영역을 수행 중인 경우 다른 모든 프로세스들은 그 임계 영역에 들어가지 못하게 막는 것

#### Progress(진행)

  > 임계 영역에 들어간 프로세스가 없다면 임계 영역에 들어가려는 프로세스가 있을 때 들어가게 해주는 것. 
  
  즉, 임계영역에 있는 프로세스 외에는 다른 프로세스가 임계 영역에 진입하는 것을 방해하면 안된다.

#### Bounded Waiting(한정 대기)

  > 프로세스가 임계 영역에 들어가려고 요청한 후부터 다른 프로세스들이 임계 영역에 들어가는 횟수에 한계를 두는 것.
  
  임계 영역에 한 번 들어갔다 나온 프로세스는 다음에 들어갈 떄 제한을 준다.
  - 기아(starvation) 상태 방지
