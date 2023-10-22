# Normalization(정규화)
> 데이터의 중복을 줄이고 무결성을 향상 시키는 등 여러 목적을 달성하기 위해 관계형 데이터베이스를 정규화된 형태로 재디자인하는 것

<br>

## 정규화의 목적
+ 불필요한 데이터 제거, 데이터 중복 최소화
+ DB 구조 확장시 재디자인 최소화
+ 이상현상(Anomaly) 방지
+ 무결성 제약조건의 시행

<br> 

## 제 1 정규화
> 테이블의 컬럼이 원자값(Atomic Value, 하나의 값)을 갖도록 테이블을 분해하는 것

### - 제 1정규형 만족하는 테이블
<img width="742" alt="스크린샷 2023-10-22 오후 5 04 00" src="https://github.com/seonyoung42/CS_Book/assets/77603632/77f2eed8-bfc9-41e8-addd-03bf10f5a262">

+ 어떤 Relation에 속한 모든 Domain이 원자값(atomic value)만으로 되어 있음 
+ 모든 attribute에 반복되는 그룹(repeating group)이 나타나지 않음
+ 기본 키를 사용하여 관련 데이터의 각 집합을 고유하게 식별할 수 있음 

<br> 

## 제 2 정규화
>  제1 정규화를 진행한 테이블에 대해 완전 함수 종속을 만족하도록 테이블을 분해하는 것
> + 완전 함수 종속: 기본키의 부분집합이 결정자가 되어선 안된다는 것


예를 들어,  {X1, X2} -> Y일 경우
+ X1와 X2가 Y의 값을 결정하면 **완전 함수적 종속**
+ X1, X2 중 하나만 Y의 값을 결정하면 **부분 함수적 종속**이라고 한다. 

<br>

<img width="753" alt="스크린샷 2023-10-22 오후 5 08 20" src="https://github.com/seonyoung42/CS_Book/assets/77603632/940636d5-bab6-4af2-9ceb-1ba492494a96">

+ 위 테이블에서는 {Model, Manufacturer} -> Manufacturer Country 의 관계를 갖고 있는데 Manufacturer만으로 Manufacturer Country 값이 결정되기 때문에 부분 함수적 종속이다.

<br> 

<img width="571" alt="스크린샷 2023-10-22 오후 5 10 48" src="https://github.com/seonyoung42/CS_Book/assets/77603632/a0b5d31f-d35f-483c-a90b-ff978a6a80bc">
<img width="732" alt="스크린샷 2023-10-22 오후 5 10 59" src="https://github.com/seonyoung42/CS_Book/assets/77603632/9a6a52bd-7c7b-4dc3-8ed5-24b83f9fbe1d">

+ 따라서 부분 함수 종속을 제거하면 다음과 같은 테이블이 된다.


<br> 

## 제 3 정규화
> 제2 정규화를 진행한 테이블에 대해 이행적 종속을 없애도록 테이블을 분해하는 것
> 이행적 종속: A -> B, B -> C가 성립할 때 A -> C가 성립되는 것

<img width="757" alt="스크린샷 2023-10-22 오후 5 14 46" src="https://github.com/seonyoung42/CS_Book/assets/77603632/eb9a30c1-e257-4ef1-ad61-35382897bfd8">

+ 위 테이블에서는 Winner Date of Birth가 Winner를 거쳐 {Tournament, Year}에 의존하고 있기 때문에 테이블을 분해해야한다.

<img width="752" alt="스크린샷 2023-10-22 오후 5 14 59" src="https://github.com/seonyoung42/CS_Book/assets/77603632/2c11e600-717c-4efa-b6df-7caf34018ad2">

+ (Tournament, Year, Winner) 테이블과
+ (Winner, Winner Date of Birth) 테이블로 분해

<br> 

## Ref
https://mangkyu.tistory.com/110
https://wkdtjsgur100.github.io/database-normalization/
