# 0622_Static

클래스 내에서 모든 객체가 공통으로 사용하는 변수가 있을 때 사용함.

공통으로 같이 쓰겠다고 명시하는 지정자가 static임

``` java
class Test {
    static int value = 200; // 클래스 변수 선언
    int number;

    public Test(int num) {
        number = num;
    }
}

public class UseTest {
    public static void main(String[] args) {
        Test t1 = new Test(1);
        Test t2 = new Test(2);

        System.out.println(t1.number); // 1 (인스턴스 변수)
        System.out.println(Test.value); // 200 (클래스 변수)
        System.out.println(t1.value); // 200 (클래스 변수를 인스턴스명으로 사용)
        System.out.println(t1.value); // 200 (클래스 변수를 인스턴스명으로 사용)
    }
}
```

static 변수만 있는 것이 아니라 static 메소드도 만들 수 있다.

static 메소드는 매개변수로 static 변수만 받을 수 있다.

``` java
class Test {
    static int value = 200; // 클래스 변수 선언
    int number;

    public Test(int num) {
        number = num;
    }

    static void printValue() { // static 메소드 선언
        System.out.println(value); 
    }
}

public class UseTest {
    public static void main(String[] args) {
        Test t1 = new Test(1);
        Test t2 = new Test(2);

        System.out.println(t1.number); // 1 (인스턴스 변수)
        System.out.println(Test.value); // 200 (클래스 변수)
        System.out.println(t1.value); // 200 (클래스 변수를 인스턴스명으로 사용)
        System.out.println(t1.value); // 200 (클래스 변수를 인스턴스명으로 사용)

        Test.printValue(); // 200 (클래스 이름으로 static 메소드 호출 가능)
        t1.printValue(); // 200 (인스턴스명으로 static 메소드 호출 가능)
    }
}
```