# Inheritance
## 상속
### 상속이란?
![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F92eb6449-2423-4fb7-86f1-2234e36c717e%2FUntitled.png?table=block&id=895aa882-002a-4c49-8f9e-2199f47c9a9e&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=1490&userId=4edf0bd8-bcb2-4c86-86ec-9d2ed1bcd09e&cache=v2)
- 기존의 클래스를 재사용하는 방식
- 클래스간 계층 구조 형성

### 상속의 특징
- 부모 클래스에서 정의된 필드와 메소드 물려받음
- 새로운 필드와 메소드 추가 가능
- 물려받은 메소드 수정 가능

### 상속의 형식

```java
class Animal {
    String name;

    public void cry() {
        System.out.println(name + " is crying.");
    }
}

class Dog extends Animal {

    Dog(String name) {
        this.name = name;
    }

    public void swim() {
        System.out.println(name + " is swimming!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog("코코");
        dog.cry();
        dog.swim();
        
        Animal dog2 = dog;
        dog2.cry();
//        dog2.swim(); // compile error
    }
}
```
- Dog는 Animal을 상속 받아 만들어짐

## 오버로딩 vs 오버라이딩
- 오버 로딩
    - 자바의 한 클래스 내에 이미 사용하려는 이름과 `같은 이름을 가진 메소드`가 있더라도 `매개변수의 개수 또는 타입이 다르면`, `같은 이름을 사용해서 메소드를 정의`할 수 있다
    ``` java
    class OverloadingMethods {
        public void print() {
            System.out.println("오버로딩1");
        }

        String print(Integer a) {
            System.out.println("오버로딩2");
            return a.toString();
        }

        void print(String a) {
            System.out.println("오버로딩3");
            System.out.println(a);
        }

        String print(Integer a, Integer b) {
            System.out.println("오버로딩4");
            return a.toString() + b.toString();
        }

    }
    ```

- 오버라이딩
    - 부모 클래스로부터 `상속받은 메소드`를 자식 클래스에서 `재정의`하는 것
    ```java
    class Person {
        void cry() {
            System.out.println("흑흑");
        }
    }

    class Child extends Person {
        @Override
        protected void cry() {
            System.out.println("잉잉");
        }
    }

    class Senior extends Person {
        @Override
        public void cry() {
            System.out.println("훌쩍훌쩍");
        }
    }
    ```