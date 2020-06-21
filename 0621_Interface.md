# 0621_Interface

## 추상 클래스

메소드를 정의하지 않고 이름만 정해둔 클래스

실제 메소드의 정의는 상속받는 자식 클래스에서 정의하도록 함.

정의하지 않은 메소드가 하나라도 있으면 추상 클래스이다.

abstract 키워드를 사용하여 추상 클래스와 추상 메소드를 선언한다.

``` java
public abstract class Test { // 추상 클래스 선언
    public void print() {
        System.out.println("일반 메소드");
    }

    public abstract void printAbstract(); // 추상 메소드 선언
}

public class AbstractTest extends Test{ // 추상 클래스를 상속받음
    public void printAbstract() { // 추상 메소드 정의
        System.out.println("추상 메소드");
    }
}
```
이처럼 추상 클래스에서 선언한 추상 메소드를 자식 클래스에서 정의할 수 있다.

## 인터페이스

상수와 메소드 이름만으로 구성되어 있다.

멤버 변수 대신 상수만 쓸 수 있고, 메소드 대신 메소드 이름만 쓸 수 있다.

``` java
public interface Test {
    int value = 10;
    void print();
}
```
위 처럼 interface 키워드를 사용하여 인터페이스를 선언할 수 있다.

implements 키워드를 통해 클래스에서 인터페이스로

``` java
public interface TestInterface {
    void print(String str);
}

public class TestClass implements TestInterface {
    public void print(String str) {
        System.out.println(str);
    }
}

public class TestMain {
    public static void main(String[] args) {
        TestInterface test = new TestClass();
        test.print("Java"); // Java
    }
}
```