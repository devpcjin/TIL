# 변수와 자료형
## 변수
### 변수 이름 정하기
- 영문자나 숫자를 사용할 수 있고, 특수문자 중에는 $,_만 사용할 수 있음
- 숫자로 시작할 수 없음
- 이미 사용 중인 예약어 사용 불가

## 자료형
||정수형|문자형|실수형|논리형|
|:-:|:--------:|:-----:|:-----:|:----:|
|1바이트|byte|-|-|boolean|
|2바이트|short|char|-|-|
|4바이트|int|-|float|-|
|8바이트|long|-|double|-|

### 배열
- `자료형[] 변수 = new 자료형[배열의 크기]`의 형태로 선언
-  배열의 크기
    - 0 ~ (배열의 크기 -1) (0부터 시작하기 때문에)
```java
    String sparta = "sparta !!";
    System.out.println(sparta);

    int[] intArray = new int[] {1,2,3,4,5}; // int 배열을 선언과 동시에 초기화
    System.out.println(Arrays.toString(intArray));
```