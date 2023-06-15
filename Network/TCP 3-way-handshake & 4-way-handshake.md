# TCP 3-way-handshake & 4-way-handshake
> TCP 프로토콜을 연결 관리를 위해 3-way-handshake와 4-way-handshake 과정을 진행한다.

<br>

## 3-way-handshake ⇒ 연결 설정
> TCP는 정확한 전송을 보장하고자 통신하기 전, 접속을 성립하기 위해 3 way handshake 과정을 진행한다.

![image-8](https://github.com/seonyoung42/CS_Book/assets/77603632/22a65f05-d30b-4d92-9fbc-a2bda6e000cc)


1. 클라이언트가 서버에게 SYN 패킷을 보낸다. (sequence: x)
2. 서버가 SYN(x)를 받고, 클라이언트에게 받았다는 신호인 ACK와 SYN 패킷을 보낸다. (sequence: y, ACK: x+1)
3. 클라이언트는 서버로부터 ACK(x+1)와 SYN(y) 패킷을 받고, ACK(y+1)를 서버로 보낸다.


<br>

## 4-way-handshake ⇒ 연결 해제
> 연결 성립 후, 모든 통신이 끝났다면 연결을 해제하기 위해 4-way-handshake 과정이 완료되어야한다.

![image-9](https://github.com/seonyoung42/CS_Book/assets/77603632/ef6cdf85-e33a-4745-92c9-9096594e75c8)

1. 클라이언트는 서버에게 연결을 종료한다는 FIN 플래그를 보낸다.
2. 서버는 FIN을 받고, 확인했다는 ACK를 클라이언트에게 보낸다. 
    1. 이때 모든 데이터를 보내기 위해 CLOSE_WAIT 상태가 된다.
    2. 데이터를 모두 보냈다면, 연결이 종료되었다는 FIN 플래그를 클라이언트에게 보낸다.
3. 클라이언트는 FIN을 받고, 확인했다는 ACK를 서버에게 보낸다. 
    1. 아직 서버로부터 받지 못한 데이터가 있을 수 있으므로 TIME_WAIT를 통해 기다린다.
4. 서버는 ACK를 받은 이후 소켓을 닫는다. (Closed)
5. TIME_WAIT 시간이 끝나면 클라이언트도 닫는다. (Closed)
