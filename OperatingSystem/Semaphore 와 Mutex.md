# Semaphore
> 멀티 프로그래밍에서 공유된 자원에 대한 접근을 제한하는 방법
> 
> 사용하고 있는 프로세스/스레드 의 수를 공통으로 관리하는 하나의 값을 사용하여 상호 배제를 달성한다.

<br>
<br>

![Untitled](https://github.com/seonyoung42/CS_Book/assets/77603632/cc3eb001-7e81-42b4-b8e4-872258dcdc16)

공유 자원에 접근할 수 있는 프로세스의 최대 허용치만큼 동시에 사용자가 접근할 수 있다.

- 각 프로세스는 세마포어의 값을 확인하고 변경할 수 있다.
- 자원을 사용하지 않는 상태가 될 때, 대기하던 프로세스가 즉시 자원을 사용한다.
- 이미 다른 프로세스에 의해 사용중이라는 사실을 알게 되면, 재시도 전에 일정시간 대기해야 한다.
- 세마포어를 사용하는 프로세스는 세마포어의 값을 확인하고, 자원을 사용하는 동안에는 세마포어의 값을 변경함으로써 다른 세마포어 사용자들이 대기하도록 한다.

<br>
<br>

# Mutex
> 동시 프로그래밍에서 공유 불가능한 자원의 동시 사용을 피하기 위해 사용하는 알고리즘
> 
> 임계 구역을 가진 스레드들의 실행 시간이 서로 겹치지 않고 각각 단독으로 실행(상호 배제)되도록 하는 기술

<br>

![Untitled-3](https://github.com/seonyoung42/CS_Book/assets/77603632/cf229678-4c9d-4085-bdc9-fa106420d9b8)

해당 접근을 조율하기 위해 lock과 unlock을 사용한다.

+ lock : 현재 임계 구역에 들어갈 권한을 얻음 ( 만약 다른 프로세스/스레드가 임계 구역 수행 중이면 종료할 때까지 대기 )
+ unlock : 현재 임계 구역을 모두 사용했음 ( 대기 중인 다른 프로세스/스레드가 임계 구역에 진입할 수 있음 )

<br>
<br>

# Semaphore VS Mutex

<p float="left">
<img src = "https://github.com/seonyoung42/CS_Book/assets/77603632/6f2ba584-7cdd-40b2-8f26-574df9ed576c" width="400" height="300">  
<img src = "https://github.com/seonyoung42/CS_Book/assets/77603632/a88841fb-a39a-49a1-973c-f4f3b6d8c847" width="400" height="300">  
</p>

+ Semaphore는 공통으로 관리하는 하나의 값(Num of Empty rooms)을 이용해 상호배제를 달성한다.
+ Mutex는 Key 에 해당하는 어떤 오브젝트를 소유한 (쓰레드,프로세스) 만이 공유자원에 접근할 수 있게 하여 상호배제를 달성한다.

<br>

### Semphore와 Mutex의 차이
#### 1. 동기화 대상의 갯수
- Mutex는 동기화 대상이 하나 
- Semaphore는 동기화 대상이 하나 이상

<br>

#### 2. Semaphore ↔ Mutex
- Semaphore는 Mutex가 될 수 있지만, Mutex는 Semaphore가 될 수 없다.
    - Mutex는 0, 1로 이루어진 이진 상태를 가지므로 Binary Semaphore로 불리기도 한다

<br>

#### 3. 자원 소유 및 책임
- Mutex는 자원을 소유할 수 있고 책임을 가짐
    - Mutex는 0, 1의 상태를 가지므로 Lock 가질 수 있음
- Semaphore는 자원을 소유할 수 없음

<br>

#### 4. 해지
- Mutex는 소유하고 있는 스레드만이 이 Mutex 해제 가능
- Semaphore는 Semaphore를 소유하지 않는 스레드도 Semaphore 해제 가능

<br>

## References 🙇🏻
+ https://chelseashin.tistory.com/40
+ https://worthpreading.tistory.com/90
