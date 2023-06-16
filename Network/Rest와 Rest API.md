# Restful API
> REST 아키텍처 스타일의 디자인 원칙을 준수하는 API

<br>

## REST API 구성
+ 자원(RESOURCE) - URI
+ 행위(Verb) - HTTP METHOD
+ 표현(Representations)

<br>

## REST 스타일
### 1. Client-server 구조
> 서버는 API 제공, 클라이언트는 사용자 인증이나 컨텍스트(세션, 로그인 정보)등을 직접 관리하는 구조

+ 각자의 역할이 확실히 구분되기 때문에 클라이언트와 서버에서 개발해야 할 내용이 명확해지고 서로간 의존성이 줄어든다.

### 2. Stateless
> 작업을 위한 상태정보를 따로 저장하고 관리하지 않는다.

+ 세션 정보나 쿠키정보를 별도로 저장하고 관리하지 않기때문에 API 서버는 들어오는 요청만을 단순히 처리한다.
+ 서비스의 자유도가 높아지고 서버에서 불필요한 정보를 관리하지 않음으로써 구현이 단순해진다.

### 3. Cacheable
> HTTP라는 기존 웹표준을 그대로 사용하기 때문에, 웹에서 사용하는 기존 인프라를 그대로 활용 가능하다.
> 
> 따라서 HTTP가 가진 캐싱 기능이 적용 가능

+ HTTP 프로토콜 표준에서 사용하는 Last-Modified태그나 E-Tag를 이용해 캐싱 구현이 가능하다

### 4. Uniform interface
> URI로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일

### 5. Layered system
> REST 서버는 다중 계층으로 구성될 수 있다

+ 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상의 유연성을 둘 수 있다.
+ PROXY, 게이트웨이 같은 네트워크 기반의 중간매체를 사용할 수 있다.

### 6. Self-descriptiveness (자체 표현 구조)
> REST API 메시지만 보고도 이를 쉽게 이해 할 수 있는 자체 표현 구조로 되어 있다

<br>

## REST API 중심 규칙
> 1. URI는 정보의 자원만을 표현
> 2. 자원에 대한 행위는 HTTP Method로 표현

```
GET /members/delete/1  --> (x)
DELETE /members/1      --> (ㅇ)
```
<br>


## 참고
https://meetup.nhncloud.com/posts/92
https://velog.io/@willis18/IOS-로드맵-RESTful-APIs
