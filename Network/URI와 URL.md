# URI와 URL
> URI는 자원의 식별자
> 
> URL은 자원에 접근할 수 있는 경로도 함께 제공하는 식별자
>  
> ex) URI : google.com / URL : https://google.com

<br>
<br>

<img width="719" alt="스크린샷 2023-06-16 오후 5 02 55" src="https://github.com/seonyoung42/CS_Book/assets/77603632/6df080a0-5e60-44c7-b22c-d791a26f1990">

+ 따라서 위와 같이 모든 URL은 URI가 될 수 있지만, 모든 URI는 URL이 될 수 없는 관계를 가진다.

<br>
<br>

## URI, URL, 그리고 URN
### URI
> URI (Uniform Resource Identifier) 는 인터넷의 자원을 식별하는 식별자

+ 자원을 이름, 위치 혹은 두 가지 모두로 식별한다.
+ URI는 URL과 URN으로 나눠진다.

### URL
> URL (Uniform Resource Locator) 은 자원뿐만 아니라 그 자원에 도달하는 방법을 나타내는 URI 타입

+ http://, ftp://, or mailto://

### URN
> URN (Uniform Resource Name) 은 특정 명명 체계를 사용하는 URI 유형

+ urn:isbn:0-486-27557-4, urn:isbn:0-395-36341-1.

<br>
즉, URI와 URN은 이름이고 URL은 이름과 주소가 결합된 URI의 하위 유형이다.

<br>
<br>

## URL 구조
<img width="647" alt="스크린샷 2023-06-16 오후 5 21 47" src="https://github.com/seonyoung42/CS_Book/assets/77603632/4d752869-4fe7-4bfa-aeca-db08387be9bd">

<br>

+ Scheme : 상호 작용하는 데 사용하는 프로토콜
+ Authority : 접근하려는 대상(userinfo, host, port로 구성)
+ Path : Host에게 요청하는 리소스
+ Query : 웹 애플리케이션 내에서 사용되는 매개변수
+ Fragment : 지정된 페이지 내에서 이동할 대상

<br>

## 참고
https://danielmiessler.com/p/difference-between-uri-url/
