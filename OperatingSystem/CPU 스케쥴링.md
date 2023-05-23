# CPU 스케쥴링
> 운영체제가 CPU의 자원을 어떤 프로세스에게 할당해 줄 지 결정하는 것

프로세스 간 우선순위를 두고, Context Switching을 할 때 우선순위가 가장 높은 프로세스에게 CPU 자원을 할당해 주는 것이다. 

<br>

## CPU 스케쥴링 기법 - 비선점 스케쥴링
> 현재 실행 중인 프로세스의 작업이 완료될 때까지 다른 프로세스가 CPU를 점유할 수 없는 스케쥴링 방식

+ 장점 : Context Switching 최소화, 처리 시간 예측 용이
+ 단점 : 긴급한 프로세스 처리 어려움

<br>

#### 1) FCFS (First come First serve) 
> 도착한 순서대로 CPU에 할당

#### 2) SJF (Shortest Job First)
> CPU 처리 시간이 짧은 순서대로 CPU에 할당
+ 평균 대기 시간을 가장 짧게 만들어 주지만, 처리 시간이 긴 프로세스는 무한정 기다리게 되는 기아상태 발생할 수 있다.

#### 3) HRN(Highest Response Ratio Next)
> CPU 처리 시간과 Ready Queue에서 대기한 시간을 고려하여 우선순위 결정
> 
> (대기 시간 + CPU 처리 시간) / CPU 처리 시간) 으로 우선순위 결정

+ 기다린 시간에 비례하여 우선순위를 높이는 기법을 에이징(Aging) 기법이라고 한다.

<br>

## CPU 스케쥴링 기법 - 선점 스케쥴링
> 우선순위가 높은 프로세스가 현재 실행 중인 프로세스의 점유를 빼앗을 수 있는 스케쥴링 방식

+ 장점 : 긴급한 프로세스 처리 가능
+ 단점 : Context Switching 자주 발생, 처리 시간 예측 어려움

<br>

#### 1) SRT (Shortest Remaining Time)
> CPU 처리 시간이 짧은 순서대로 CPU에 할당하는 방식
+ SJF의 선점형 방식이다

#### 2) 라운드로빈
> 동일한 시간의 Time Quantum 만큼 CPU를 할달 받는 방식
> 
> 시간이 지나면 CPU를 회수하고 해당 프로세스를 ready queue의 제일 마지막으로 보냄

+ Time Quantum or Time Slice : 실행의 최소 단위 시간

#### 3) 다단계 큐
> 프로세스를 여러 그룹으로 나누고 그룹마다 ready queue를 가지는 방식
> 
> 각 ready queue마다 다른 스케쥴링 방식을 선택할 수 있다.

+ 예를 들어, 사용자와 상호작용하는 Foreground Queue에는 라운드 로빈 방식을, 백그라운드에서 돌아가는 프로세스가 모인 Background Queue에는 FCFS 방식을 적용할 수 있다.


