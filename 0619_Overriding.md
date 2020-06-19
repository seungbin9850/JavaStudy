# 0619_Overriding

## 오버라이딩

자식 클래스에서 메소드를 재정의하여 사용하는 것

메소드의 명칭은 그대로 두고, 기능을 새롭게 정의해서 사용한다.

``` java
public class TestClass {
    public void print() {
        System.out.println("부모 클래스 메소드");
    };
}

public class OverridingClass extends TestClass {
    public void print() {
        System.out.println("자식 클래스 메소드");
    }
}

public class UseTest {
    public static void main(String[] args) {
        TestClass test = new TestClass();
        test.print(); // 부모 클래스 메소드

        OverridingClass over = new OverridingClass();
        over.print(); //자식 클래스 메소드
    }
}
```
위 코드처럼 자식 클래스가 부모 클래스의 메소드와 같은 이름으로 메소드를 선언하여 사용할 수 있다.

그 경우에, 메소드를 재정의 할 수 있다. 
``` java
public class TestClass {
    public void print() {
        System.out.println("부모 클래스 메소드");
    };
}

public class OverridingClass extends TestClass {
    public void print() {
        System.out.println("자식 클래스 메소드");
    }
}

public class UseTest {
    public static void main(String[] args) {
        TestClass test = new TestClass();
        test.print(); // 부모 클래스 메소드

        OverridingClass over = new OverridingClass();
        over.print(); //자식 클래스 메소드
    }
}
```

## 다형성

부모 클래스 변수로 자식 클래스를 사용하는 것

``` java
public class UseTest {
    public static void main(String[] args) {
        TestClass test = new TestClass();
        test.print(); // 부모 클래스 메소드

        OverridingClass over = new OverridingClass();
        over.print(); // 자식 클래스 메소드

        TestClass overTest = new OverridingClass();
        overTest.print(); // 자식 클래스 메소드
    }
}
```
이처럼 부모 클래스 변수를 자식 클래스 생성자로 생성할 수 있다.

이 때 부모 클래스의 메소드는 자식 클래스에서 재정의한 메소드로 실행된다.

## 멤버변수 오버라이딩

멤버변수도 상속된 자식클래스에서 재정의 할 수 있다.

멤버 변수는 실제로 참조하는 클래스의 변수가 아닌, 그냥 참조변수의 타입에 따라 값을 가져온다.

``` java
public class TestClass {
    public int num = 1;

    public void print() {
        System.out.println("부모 클래스 메소드");
    };
}

public class OverridingClass extends TestClass {
    public int num = 2;

    public void print() {
        System.out.println("자식 클래스 메소드");
    }
}

public class UseTest {
    public static void main(String[] args) {
        TestClass test = new TestClass();
        test.print(); // 부모 클래스 메소드

        OverridingClass over = new OverridingClass();
        over.print(); // 자식 클래스 메소드

        TestClass overTest = new OverridingClass();
        overTest.print(); // 자식 클래스 메소드
        System.out.println(overTest.num); // 1
    }
}
```