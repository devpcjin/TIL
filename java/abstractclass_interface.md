# 추상 클래스, 인터페이스
## 추상클래스 (Abstract Class)
### 추상 클래스란?
- 추상메소드를 선언할 수 있는 클래스
- 상속받는 클래스 없이 그 자체로 인스턴스 생성 불가능

### 추상 메소드
- 설계만 되어있고 수행되는 코드는 없는 메소드
- 상속받는 클래스 마다 작성자가 작성해서 다른 동작 수행
-  형식
    ```java 
    abstract 리턴타입 메소드이름();
    ```

## 인터페이스(Interface)
### 인터페이스란?
- 객체의 특정 행동의 특징을 정의하는 간단한 문법
- 형식
    ```java
        interface 인터페이스명{
        public abstract void 추상메서드명();
        }
    ```

## 인터페이스 VS 추상 클래스
|인터페이스|추상클래스|
|---|---|
|구현하려는 객체의 동작의 명세|클래스를 상속 받아 이용 및 확장을 위함|
|다중 상속 가능|다중 상속 불가능 , 단일 상속|
|`implements`를 이용하여 구현|`extends`를 이용하여 구현|
|메소드 시그니처(이름, 파라미터, 리턴 타입)에 대한 선언만 가능|추상메소드에 대한 구현 가능|