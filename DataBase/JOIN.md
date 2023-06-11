# JOIN
> 둘 이상의 테이블을 결합하는 것으로, 데이터 조회 시 다른 테이블의 데이터토 함께 조회해야할 때 사용된다.
> 
> 따라서, 결합하려는 테이블들이 적어도 하나의 컬럼을 공유하고 있어야 한다.

<br>

<img width="628" alt="스크린샷 2023-06-11 오후 8 46 44" src="https://github.com/seonyoung42/CS_Book/assets/77603632/d764e090-936c-4ad5-afb4-59d043ef2999">

## INNER JOIN(내부 조인)
> 공통적인 부분(교집합) 만 select하는 조인

+ 일반적으로 JOIN은 내부 조인을 의미


```sql
SELECT A.ID ID, A.NAME NAME, B.GENDER GENDER
FROM TableA as A       	
INNER JOIN TableB as B  
ON A.ID = B.ID
```

<img width="402" alt="스크린샷 2023-06-11 오후 8 54 45" src="https://github.com/seonyoung42/CS_Book/assets/77603632/2e31bdf7-5263-46fb-8a9d-a861dec127d8">

<br>
<br>

## OUTER JOIN(외부 조인)
> 통 데이터 외에 어느 한 테이블에만 존재하는 데이터도 함께 결합하여 조회하고자 할 때 사용하는 조인
+ 내부 조인은 공통된 컬럼을 기준으로 테이블을 묶기 때문에 순서가 상관이 없지만 외부 조인에서는 순서가 중요함

<br>

### 1. LEFT JOIN
> 왼쪽 테이블을 기준으로 Select하는 조인

```sql
SELECT A.ID ID, A.NAME NAME, B.GENDER GENDER
FROM TableA as A       
LEFT JOIN TableB as B   
ON A.ID = B.ID
```


<img width="404" alt="스크린샷 2023-06-11 오후 9 00 31" src="https://github.com/seonyoung42/CS_Book/assets/77603632/45bd974d-e397-4d48-9115-0e5ba27f30dc">

LEFT JOIN 명령문 오른쪽에 위치한 테이블(Table A)을 기준으로 조인되었으며 왼쪽 테이블의 모든 데이터와 오른쪽 테이블의 중복 데이터가 결합되었다. 

값이 없는 데이터는 null로 표시 된다.

<br>
<br>

### 2. RIGHT JOIN
> 오른쪽 테이블을 기준으로 Select하는 조인


```sql
SELECT A.ID ID, A.NAME NAME, B.GENDER GENDER
FROM TableA as A       
RIGHT JOIN TableB as B   
ON A.ID = B.ID
```
<img width="401" alt="스크린샷 2023-06-11 오후 9 15 18" src="https://github.com/seonyoung42/CS_Book/assets/77603632/a57851ea-7ce8-4be7-984a-450f2c3e5ad5">

RIGHT JOIN 명령문 오른쪽에 위치한 테이블(Table B)을 기준으로 조인되었으며 오른쪽 테이블의 모든 데이터와 왼쪽 테이블의 중복 데이터가 결합되었다. 

값이 없는 데이터는 null로 표시 된다.


<br>
<br>

### 3. FULL JOIN
> 왼쪽 또는 오른쪽 테이블의 모든 값이 출력되는 조인

```sql
SELECT A.ID ID, A.NAME NAME, B.GENDER GENDER
FROM TableA as A       
FULL JOIN TableB as B   
ON A.ID = B.ID
```

<img width="398" alt="스크린샷 2023-06-11 오후 9 18 07" src="https://github.com/seonyoung42/CS_Book/assets/77603632/dd708931-f4a4-4c22-a4d1-7804eba496e0">

<br>
<br>

## 🙇🏻‍♀️ 참고
https://velog.io/@newdana01/Database-테이블-조인-이해하기
