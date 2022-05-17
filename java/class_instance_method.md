# Class, Instance, Medthod
## Class
### 클래스란?
- 표현하고자 하는 대상의 공통 속성을 한 군데에 정의해 놓은 것
    - 객체의 속성의 정의해 놓은 것
- 멤버변수
    - 클래스 내부의 정보

    ```java
        class Phone {
            String model;
            String color;
            int price;
        }
    ```

## Instance
### 인스턴스란?
- 어떠한 `Class`로 부터 만들어진 객체

    ```java
        Phone galaxy = new Phone();
        galaxy.model = "Galaxy10";
        galaxy.color = "Black";
        galaxy.price = 100;

        Phone iphone =new Phone();
        iphone.model = "iPhoneX";
        iphone.color = "Black";
        iphone.price = 200;
    ```
    - `galaxy`와 `iphone`는 Phone 클래스의 인스턴스

## Method
### 메소드란?
- 작업을 수행하는 코드를 하나로 묶어 놓은 것

### 메소드가 필요한 이유?
- 재사용성
    - 반복적으로 재사용 가능
- 중복된 코드 제거
    - 중복된 코드를 없애 효율적인 코드 작성
- 프로그램의 구조화
    ```java
        int[] heights = new int[5]; // 키가 들어가 있는 배열

        initHeight(heights); // 1. 키에 대한 초기화
        sortHeight(heights); // 2. 키를 오름차순으로 정렬
        printHeight(heights); // 3. 정렬된 키를 출력
    ```

### 메소드 선언과 구현
```shell
    반환타입 메소드이름 (타입 변수명,타입 변수명, ...){ 
        수행되어야 할 코드
    }
```
- 예제
    ```java
        class Calculation {
            int add(int x, int y) {
                int result = x + y;
                return result;
            }// 두 값을 더한 결과

            int subtract(int x, int y) {
                int result = x - y;
                return result;
            }// 두 값을 뺀 결과 
        }

        public class Main {
            public static void main(String[] args) {
                Calculation calculation = new Calculation();
                int addResult = calculation.add(100, 90);
                int subResult = calculation.subtract(90, 70);

                System.out.println("두 개를 더한 값은 " + addResult);
                System.out.println("두 개를 뺀 값은 " + subResult);
            }
        }
    ```