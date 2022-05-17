# Constructor
## 생성자 (Constructor)
### 생성자 란?
- 인스턴스가 생성될 때 사용되는 `인스턴스 초기화 메소드`
    - `new`와 같은 키워드로 해당 클래스의 인스턴스가 생성될 때, 자동으로 호출
    - 인스턴스 변수를 초기화하는 용도로 사용

### 생성자의 형식
```java
    클래스이름 (타입 변수명, 타입 변수명, ...){
        인스턴스 생성 될 때에 수행하여할 코드
        변수의 초기화 코드
    }
```
- 클래스 명과 생성자의 이름은 같아야함
- `return`값이 없음

    ```java
        class Phone {
        String model;
        String color;
        int price;

        Phone(String model, String color, int price){ // 생성자
            this.model = model;
            this.model = color;
            this.price = price;
        }
    ```
