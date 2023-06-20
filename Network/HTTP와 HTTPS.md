# HTTP (= HyperText Transfer Protocol)
> 클라이언트와 서버가 자원을 주고받을 때 사용하는 통신 규약
+ OSI 7계층 중, 응용 계층의 프로토콜로 TCP/IP 위에서 작동하는 프로토콜

<br>

## HTTP의 구조
![images-nonasking-post-37e4780a-7aef-4025-8e3d-18a661141578-%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%2C%202021-12-09%2011-00-57](https://github.com/seonyoung42/CS_Book/assets/77603632/84ff7422-a39a-44e2-b072-8142750e0bef)

### StartLine
> 요청(request)의 첫번째 줄에 해당하는 부분으로 세 부분으로 나눠짐

+ HTTP Method: 해당 요청의 액션을 정의하는 부분 ex) GET, POST, DELETE
+ Request target: 해당 요청이 전송되는 목표 url
+ HTTP Version: 사용되는 HTTP 버전
  + HTTP/3까지 개발되어 있고 1.1 버전이 가장 보편적으로 사용된다.
 
  
<br>

### Headers
> 요청(request)에 대한 메타 데이터(추가 정보)를 담고있는 부분으로 key : value 형태로 구성

+ Host : 요청을 보내는 목표(타겟)의 주소. ex) www.apple.co.kr
+ User-Agent: 요청을 보내는 클라이언트에 대한 정보 ex) chrome, firefox, safari, explorer
+ Content-Type: 해당 요청이 보내는 메세지 body의 타입 ex) application/json
+ Content-Length: body의 길이
+ Authorization: 회원의 인증/인가를 처리하기 위한 토큰 작성

<br>

### Body
> 요청(request)의 실제 내용이 들어가는 부분
+ 요청 Method에 따라 body가 없는 경우도 있음
    + 주로 POST 일 때 body 작성
  
<br>


## HTTP 특징
### 1. StateLess 
> 상태 정보를 따로 저장하지 않고, api서버는 들어오는 요청을 단순히 실행

+ HTTP 통신은 서로 독립적이기 때문에 과거의 통신을 기억하지 않는다. 따라서, 매 통신마다 필요한 모든 정보를 담아 요청
+ 연속된 데이터 처리가 필요한 경우를 위해 로그인 토큰, 브라우저 쿠키, 세션 같은 기술이 추가됨

<br>

### 2. 보안 처리 X
> HTTP 통신은 별도의 보안 조치가 없기 때문에 패킷을 훔쳐보는 스니핑(Sniffing) 공격에 취약

![image-6](https://github.com/seonyoung42/CS_Book/assets/77603632/8349d30a-adc7-4538-9d69-50e3c1965c71)

+ 따라서 데이터를 보호하기 위해서는 인증서를 통해 패킷을 암호화한 뒤에 전송해야 한다.

<br>

# HTTPS
> HTTP에 정보를 암호화하는 SSL이 추가된 프로토콜

![image-11](https://github.com/seonyoung42/CS_Book/assets/77603632/664343e2-54f4-4636-a435-a47052c9fb5d)
+ 기존의 HTTP 통신은 TCP 위에서 동작하였는데 이 TCP 위에 보안계층인 SSL이 올라가고 그 위에 HTTP를 얹어 보안이 보장된 통신을 하도록 하는 프로토콜이 HTTPS 이다.

<br>

## HTTPS 암호화 방식
### 1. 대칭키 암호화
> 암호화를 하는 키와 복호화를 하는 키가 동일한 방식

![Untitled-3](https://github.com/seonyoung42/CS_Book/assets/77603632/5a0dbd16-a7c6-46ef-9ec1-e17ca6278f75)
+ 암호화와 복호화 모두에 사용가능한 키를 대칭키라고 함

<br>

### 2. 비대칭키 암호화(=공개키 암호화)
> 암호화를 하는 키와 복호화를 하는 키가 다른 방식으로 두 개의 키가 필요한 방식

![Untitled-4](https://github.com/seonyoung42/CS_Book/assets/77603632/8307625b-d560-4214-b9b0-1d2ffd64b98f)
+ 공개키로 암호화하면 개인키로 복호화 할 수 있고, 개인키로 암호화하면 공개키로 복호화 할 수 있다.
+ 이렇게 한 쌍의 키로 암호화, 복호화를 하는 방식을 RSA 알고리즘이라고 한다.

<br>

## 참고
https://velog.io/@nonasking/HTTP의-특징과-구조
https://velog.io/@subinmun1997/CS-Study-6주차
