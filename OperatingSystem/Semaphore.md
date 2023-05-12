# Semaphore
> 멀티 프로그래밍에서 공유된 자원에 대한 접근을 제한하는 방법
> 
> 사용하고 있는 프로세스/스레드 의 수를 공통으로 관리하는 하나의 값을 사용하여 상호 배제를 달성한다.

<br>

![Untitled](https://github.com/seonyoung42/CS_Book/assets/77603632/cc3eb001-7e81-42b4-b8e4-872258dcdc16)

공유 자원에 접근할 수 있는 프로세스의 최대 허용치만큼 동시에 사용자가 접근할 수 있다.

- 각 프로세스는 세마포어의 값을 확인하고 변경할 수 있다.
- 자원을 사용하지 않는 상태가 될 때, 대기하던 프로세스가 즉시 자원을 사용한다.
- 이미 다른 프로세스에 의해 사용중이라는 사실을 알게 되면, 재시도 전에 일정시간 대기해야 한다.
- 세마포어를 사용하는 프로세스는 세마포어의 값을 확인하고, 자원을 사용하는 동안에는 세마포어의 값을 변경함으로써 다른 세마포어 사용자들이 대기하도록 한다.