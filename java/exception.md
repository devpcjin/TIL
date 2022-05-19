# 예외, 예외처리 (Ecxeption, Error Handling)
## 예외처리
### 예외처리란?
- 다양한 예외 상황 발생 시 대응하기 위한 코드

### 예외처리의 목적
- 예외로 인한 비정상적인 종료를 막기 위해
- 개발자에게 알려 코드를 보완할 수 있도록 요청

### Throwable
- 모든 예외 클래스는 Throwable의 자손 클래스
    - Error
        - 종료되어야하는 심각한 문제
        - 컴퓨터나 JVM이 시스템적으로 동작할 수 없는 상황
    - Exception
        - 프로그램은 종료되지 않지만 

    ![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F7e230efc-057d-49c1-9c17-fb9aa0611957%2FUntitled.png?table=block&id=f83ceecc-b086-4e11-9bac-7746b53d2855&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=2000&userId=4edf0bd8-bcb2-4c86-86ec-9d2ed1bcd09e&cache=v2)
    - RuntimeException : 실행도중 발생하는 Exception
    - IOException : 파일을 읽고 쓰거나, 원격에 있는 저장소로 부터 데이터를 읽고 쓸 때 나는 에러 표현 

### try-catch(-finally)
- 형식
    ``` java
        try {
            // 예외가 발생할 가능성이 있는 코드를 구현합니다.
        } catch (FileNotFoundException e) {
            // FileNotFoundException이 발생했을 경우,이를 처리하기 위한 코드를 구현합니다.
        } catch (IOException e) {
            // FileNotFoundException이 아닌 IOException이 발생했을 경우,이를 처리하기 위한 코드를 구현합니다.
        } finally {
            // 예외의 발생여부에 관계없이 항상 수행되어야하는 코드를 구현합니다.
        }
    ```
    - finally구문은 필수가 아님
    > 또한, 예외는 중복 catch 블럭을 사용하여 다양한 예외처리를 수행할 수 있습니다. 중복 catch블럭을 사용할 때는 먼저 선언된 catch블럭부터 확인합니다. 앞의 catch블럭에서 잡혔다면, 뒤의 catch블럭으로는 전파되지 않습니다. 좁은 범위의 예외부터 앞에 선언하는 것이 좋습니다. 여기서 좁은 범위란 상속관계에서 자식 클래스에 위치 할수록 좁은 범위입니다. 예를 들어서 `IOException`이 발생할 것 같아 예외처리를 하고, 그 외의 예외도 예외처리를 하고 싶다면 `IOException`을 catch 하는 구문을 먼저, `Exception` 을 catch하는 구문을 그 뒤에 작성합니다

### try-with-resource
- `try-catch(-finally)문`은 자원을 닫을 때 close()를 사용해야하지만, `try-with-resource문`은 try문을 벗어나는 순간 자동으로 close()가 호출
- 형식
    ```java
        import java.io.FileOutputStream;
        import java.io.IOException;

        public class Main {
            public static void main(String[] args) {

                try (FileOutputStream out = new FileOutputStream("test.txt")) {
                    // test.txt file 에 Hello Sparta 를 출력
                    out.write("Hello Sparta".getBytes());
                    out.flush();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    ```
    - try-catch문 이었다면?
        ```java
            import java.io.FileOutputStream;
            import java.io.IOException;

            public class Main {
                public static void main(String[] args) throws IOException {
                    FileOutputStream out = new FileOutputStream("test.txt");
                    try {
                        // test.txt file 에 Hello Sparta 를 출력
                        out.write("Hello Sparta".getBytes());
                        out.flush();
                    } catch (IOException e) {
                        e.printStackTrace();
                    }
                    out.close();
                }
            }
        ```

### 메소드에서의 예외 선언
```java
    void method() throws IndexOutOfBoundsException, IllegalArgumentException {
        //메소드의 내용
    }
```
- catch문을 이용해서 예외처리를 하지 않은 경우, 메소드에 throws로 예외가 발생할 수 있다는 것을 알려주어야 함