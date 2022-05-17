# Access Modifier
## 접근 제어자
- 멤버 변수/함수 혹은 클래스에 사용되며 외부에서의 접근을 제어하는 역할
    - `private` : 같은 클래스 내에서만 접근 가능
    - `default(nothin)` : 같은 패키지 내에서만 접근 가능
    - `protected` : 같은 패키지 내에서, 그리고 다른 패키지의 자손 클래스에서 접근 가능
    - `public` : 접근 제한이 없음


- ModifierTest.java
``` java
package pkg;

public class ModifierTest {
    private void messageInside() {
        System.out.println("This is private modifier");
    }

    public void messageOutside() {
        System.out.println("This is public modifier");
        messageInside();
    }

    protected void messageProtected() {
        System.out.println("This is protected modifier");
    }
}
```

- Main.java
```java
import pkg.ModifierTest;

class Child extends ModifierTest {
    void callParentProtectedMember() {
        System.out.println("Call my parent's protected method");
        super.messageProtected();
    }
}

public class Main {
    public static void main(String[] args) {
        ModifierTest modifierTest = new ModifierTest();

        modifierTest.messageOutside();
//        modifierTest.messageInside(); // compile error
//        modifierTest.messageProtected(); // compile error

        Child child = new Child();
        child.callParentProtectedMember();
    }
}
```