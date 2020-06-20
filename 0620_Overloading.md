# 0620_Overloading

## 오버로딩

같은 이름의 메소드여도 매개변수에 따라 다른 정의를 할 수 있는 것

리턴 값만 다른 메소드는 오버로딩이 안 됨.

``` java
public class Test {
    public print() { // 매개변수 없음
        System.out.println("매개변수 없음");
    }

    public print(int a) { // int형 매개변수를 받음 (오버로딩)
        System.out.println(a);
    }

    public print(String a) { // String형 매개변수를 받음 (오버로딩)
        System.out.println(a);
    }

    public print(int a, int b) { // int형 매개변수를 두 개 받음 (오버로딩)
        System.out.println(a + ", " + b);
    }
}
```
print라는 이름을 가진 메소드를 4가지 정의 했다.

각 메소드를 메인에서 실행시켜보면
``` java
public class useTest {
    public static void main(String[] args) {
        Test test = new Test();
        test.print() // 매개변수 없음
        test.print(1) // 1
        test.print("Java") // Java
        test.print(1, 2) // 1, 2
    }
}
```
모두 다른 실행 결과를 출력한다