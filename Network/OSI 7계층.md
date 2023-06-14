# OSI 7계층
> 네트워크에서 통신이 일어날 때, 처리되어야하는 작업을 순차적으로 7단계로 나눈 것

<br>

![The%207%20Layers%20of%20OSI](https://github.com/seonyoung42/CS_Book/assets/77603632/1fafd461-d6d3-4399-9a9c-066f0c2cdb3f)
+ OSI 1 ~ 3 계층은 **하드웨어 영역**으로 각 계층마다 매칭되는 하드웨어 장치가 있다. 따라서, 하드웨어가 실질적으로 해당 계층의 역할을 수행한다.
+ OSI 4 ~ 7 계층은 **소프트웨어 영역**으로 4 ~ 6 계층은 **OS**가, 7 계층은 **프로그램**이 해당 계층의 역할을 수행한다.


<br>

## 1. Physical(물리 계층)
> 실제 장치의 디지털 데이터를 전기적인 신호로 변환하는 계층
> 
> 통신 단위 : Bit / 전송 장비 : 케이블, 허브, 리피터

<br>

![images-poiuyy0420-post-1ace8506-4022-49e9-938d-f97782656a22-image](https://github.com/seonyoung42/CS_Book/assets/77603632/779a4c33-f66f-4e87-aa70-19282c744a02)


+ 데이터를 전달하기만 하고 데이터의 종류, 에러 등에는 전혀 신경쓰지 않는다.
+ 통신 단위는 0과 1로만 나타내어지는 비트로 전기적으로 On Off 상태만 표현한다.


<br>

## 2. Data Link(데이터 링크 계층)
> 물리 계층을 통해 송수신되는 정보의 오류와 흐름을 제어하여 신뢰성 있는 전송을 보장하는 계층
> 
> 통신 단위 : 프레임 / 전송 장비 : 브릿지, 스위치

<br>

![images-poiuyy0420-post-196a557a-986a-4116-9463-15c870d9b466-image](https://github.com/seonyoung42/CS_Book/assets/77603632/006eb7e3-3fa9-4b1d-96cf-e81ac3cd7629)

+ 네트워크 계층에 데이터를 전달하고, 물리 계층에서 발생할 수 있는 오류를 탐지하고 수정한다.
+ 시스템 간에 오류 없는 데이터 전송을 위해 상위 계층(=네트워크 계층)에서 받은 패킷을 프레임으로 변환하여 물리계층으로 전송한다.

<br>

## 3. Network (네트워크 계층)
> 경로(Route)와 주소(IP)를 정해서 패킷을 빠르고 안전하게 전달해주는 계층이다.
> 
> 통신 단위 : 패킷 / 전송 장비 : 라우터, IP

<br>

![images-poiuyy0420-post-acb87719-7c85-47fa-92ea-ff7367508f8a-image](https://github.com/seonyoung42/CS_Book/assets/77603632/b7b526dd-a3b3-4584-bef1-9cc9f2e5e85c)

+ 라우팅, 흐름제어, 세그멘테이션, 오류제어, 인터 네트워킹 등의 기능 수행한다.
+ 라우팅 프로토콜을 사용하여 최적의 경로를 선택하고 IP 주소를 지정하여 전송 계층으로 패킷을 전달한다.

<br>

## 4. Transport (전송 계층)
> 프로토콜을 통해 통신을 활성화하기 위한 계층으로 포트를 열어서 응용프로그램들이 전송 할 수 있게 하는 계층이다
> 
> 통신 단위 : 세그먼트 / 전송 장비 : L4 스위치 / 프로토콜 : TCP, UDP

<br>

![images-poiuyy0420-post-ac993f35-0d71-4627-b1db-21c0d63079ac-image](https://github.com/seonyoung42/CS_Book/assets/77603632/bb8d4cad-813a-497a-82f8-6e63628748c6)

+ 오류 제어, 흐름제어, 혼잡 제어 등을 수행하면서, 시스템 간에 신뢰성 있는 데이터를 전송한다.
+ 데이터 전송을 위해서 Port 번호 사용

<br>

## 5. Session(세션 계층)
> 응용 프로그램 간의 대화를 유지하기 위한 구조를 제공하고, 이를 처리하기 위해 프로세스들의 논리적인 연결을 담당하는 계층
> 
> API, Socket

<br>

![images-poiuyy0420-post-cd181df3-fd96-4c42-8b2c-d6444e841142-image](https://github.com/seonyoung42/CS_Book/assets/77603632/7683bb7a-ded3-4359-bdac-c1ccb93cdca4)
+ 통신 중 연결이 끊어지지 않도록 유지하기 위해 TCP/IP 세션 연결의 설정과 해제, 세션 메세지 전송 등의 기능 수행한다.

<br>

## 6. Presentation(표현 계층)
> 데이터의 표현 방식을 결정하는 계층 
> 
> 프로토콜 : JPEG, MPEG

<br>

![images-poiuyy0420-post-80348520-caba-46b9-8a11-b378911c421e-image](https://github.com/seonyoung42/CS_Book/assets/77603632/cb0e2087-0fad-4b84-9046-20a38e346f41)

+ 전송하는 데이터의 표현방식을 결정하는 계층 (예: 데이터 변환, 압축, 암호화 등)으로 인코딩이나 암호화 등의 동작이 표현계층에서 이루어진다

<br>

## 7. Application(응용 계층)
> 응용 프로세스와 직접 관계하여 일반적인 응용 서비스를 수행하는 계층
> 
> 프로토콜 : HTTP, FTP, SMTP, DNS 

<br>

![images-poiuyy0420-post-969dec51-5e53-4dc0-ba72-91094518932d-image](https://github.com/seonyoung42/CS_Book/assets/77603632/ad286c64-e1cc-48e2-b1cd-627a02fc0574)

+ 사용자와 가장 가까운 계층으로 응용 프로세스 간의 정보 교환, 파일 전송 등의 기능을 수행한다.
+ 사용자 인터페이스, 전자우편, 데이터베이스 관리 등의서비스를 제공한다.

<br>


