# DNS 란?
> DNS(=Domain Name System),
> 문자와 주소체계를 상호 확인 및 변환 할 수 있는 시스템

<br>

![Untitled-3](https://github.com/seonyoung42/CS_Book/assets/77603632/94ec9241-7cad-45bd-b9a6-10b16bca03c3)

DNS 란 IP 네트워크에서 사용하는 시스템으로 인터넷 접속을 위해서 URL이 가리키는 IP 주소를 반환해주는 시스템이다.

DNS Server가 웹 서버 주소에 해당하는 IP 주소 테이블을 가지고 있다.

<br>

# DNS Round Robin이란?
> DNS Server의 구성 방식 중 하나로 round-robin 방식으로 IP주소를 반환하는 것

### Round Robin 이란?
> 각 프로세스마다 CPU를 점유할 수 있는 시간을 정해두고 시간이 지나면 CPU를 회수하여 해당 프로세스를 ready queue의 제일 마지막으로 보내는 방식
+ 시분할 시스템을 위해 설계된 선점형 스케줄링 중 하나로 프로세스들 사이에 우선순위를 두지 않고 순서대로 시간단위(Time Quantum/Slice)로 CPU를 할당하는 방식의 CPU 스케줄링 알고리즘

<br>

## DNS Round-Robin의 장단점
+ 장점 : 시간에 따라 자동으로 스케쥴링이 되기 때문에 부하에 대한 걱정을 할 필요가 없고, 로드 벨런서도 필요 없음
+ 단점 : 서버의 장애 여부를 판단하지 않기때문에 회복 할 수 없음
