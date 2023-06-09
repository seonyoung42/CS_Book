# GET 
> 클라이언트에서 서버로 **정보를 요청**하기 위해 사용하는 메서드

주로 데이터를 읽거나(Read), 검색(Retrieve)할 때에 사용되는 메소드이다

<br>

## GET 호출 예시
```
www.example.com/show?name1=value1&name2=value2
```
URL 주소 끝에 Parameter로 포함되어 전송되며, 이 부분을 **쿼리 스트링**이라한다.

URL 끝에 "?"를 붙이고 그 다음 변수명1=값1&변수명2=값2... 형식으로 이어 붙이는 방식이다.

서버에서는 name1 이라는 파라미터명으로 value1이라는 값을 전달받는다.

이처럼 URL 끝에 파라미터로 전달하기때문에 GET은 body영역을 사용하지 않는다.

<br>

## GET의 특징
#### 1. GET 요청은 캐시가 가능하다

```
GET을 통해 서버에 리소스를 요청할 때 웹 캐시가 요청을 가로채 서버로부터 리소스를 다시 다운로드하는 대신 리소스의 복사본을 반환한다.
HTTP 헤더에서 cache-control 헤더를 통해 캐시 옵션을 지정할 수 있다.
```

#### 2. 데이터 길이에 대한 제한이 있다.

```
길이 제한은 표준이 따로 있는건 아니고 브라우저마다 제한이 다르다
```

#### 3. 민감한 데이터를 다룰 때 GET 요청을 사용하지 않는다
```
파라미터에 내용이 전부 노출되기 때문
```

<br>

# POST
> 클라이언트에서 서버로 **데이터를 전송**할 때 사용하는 메서드

POST는 데이터를 HTTP 메시지 body에 담아서 서버로 전송한다.

<br>

## POST 요청을 위한 Body 작성 예시

```
{
	"param1":"value1",
	"param2":"value2"
}
```

POST로 데이터를 전송할 때는 길이 제한이 없기 때문에 용량이 큰 데이터를 보낼 때 사용한다.

또한 GET 처럼 데이터가 외부적으로 드러나지 않기 때문에 보안이 중요한 곳에서도 사용된다. 

그러나 POST 요청도 크롬의 개발자 도구, Fiddler와 같은 툴로 요청 내용을 확인할 수 있기 때문에 민감한 데이터의 경우에는 반드시 암호화해서 전송해야 한다.

<br>

## POST의 특징
#### 1. 요청이 캐시되지 않는다.
#### 2. 데이터 길이에 제한이 없다.
#### 3. 서버로 보내기 전에 인코딩하고, 전송 후 서버에서 다시 디코딩한다.
#### 4. 쿼리스트링(문자열) 데이터 뿐만 아니라, 라디오 버튼, 텍스트 박스 같은 객체들의 값도 전송 가능하다.

<br>

## GET과 POST의 비교

![image-7](https://github.com/seonyoung42/CS_Book/assets/77603632/85301d0c-8320-4db5-94bb-121f5fa02276)

+ 멱등성 : 연산을 여러 번 적용하더라도 결과가 달라지지 않는 성질
    + GET은 리소스를 조회하는 것이기에 여러 번 요청하더라도 그 결과가 일정하지만 POST는 리소스를 새로 생성하거나 업데이트할 때 사용되기 때문에 그 결과가 일정하지 않다. 
<br>

## Ref
https://noahlogs.tistory.com/35
