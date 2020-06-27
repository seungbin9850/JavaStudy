# 0627_Exception

## 예외

프로그램이 실행하다가 발생하는 소프트웨어적 문제

자바에선 개발자가 코딩할 때 예외상황을 처리해야 하느냐에 따라 예외와 런타임 예외로 나뉜다.

자바에서는 예외도 클래스로 처리한다.

``` java
public class ExceptionTest {
    public static void main(String[] args) {
        String[] hello = new String[2];
        try {
            // 주 실행 코드
            // 예외 발생 가능성이 있는 코드

            hello[0] = "안녕하세요";
            hello[1] = "안녕";
            hello[2] = "하이"; 
        } catch (ArrayIndexOutOfBoundsException e) {
            // ArrayIndexOutOfBoundsException 예외가 발생하면 실행하는 부분
            // 두 칸 배열을 선언하고 세 개의 값을 넣으려 했기 때문에 발생

            System.out.println("배열 참조 에러");
        } catch (Exception e) {
            // try-catch 문에서 catch를 여러 번 쓸 수 있다.

            System.out.println(e.getMessage());
        } finally {
            // 예외가 발생하든 하지 않든 반드시 실행되는 부분

            System.out.println("시스템 종료");
        }
    }
}
```
## throws

메소드를 정의할 때 throws를 추가하면 그 메소드를 호출하는 곳에서 예외처리를 한다.

``` java
public class Test {
    void TrowsException() throws ArithmeticException {
        int a = 0;
        a = 10 / a;
    }

    public static void main(String[] args) {
        try {
            Test.ThrowsException(); // 예외를 던짐
        } catch (Exception e) {
            System.out.println("main에서 예외를 처리해준다.  " + e);
        }
    } 
} 
```

## throw

개발자의 판단에 따라 예외를 발생시키는 것

``` java
public class Test {
    public static void main(String[] args) {
        try {
            throw new Exception(); // 예외를 던지면
        } catch (Exception e) {
            System.out.println(e); // catch에서 잡아줌
        }
    }
}
```