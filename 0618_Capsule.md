# 0618_Capsule

## 접근제어 지시자

public : 외부의 접근을 혀용

private : 외부의 접근을 허용하지 않음

``` java
public class MyCalculater {
    public void calculater(int a, char b, int c) {  // public (외부 접근 허용)
        if (b == '+') {
            add(a, c);
        } else if (b == '-') {
            minus(a, c);
        } else {
            System.out.println("지원하지 않는 연산자");
        }
    }

    private void add(int a, int c) {  // private (외부 접근 허용 안함)
        System.out.println(a + c);
    }

    private void minus(int a, int c) {
        System.out.println(a - c);
    }
}
```

위처럼 public, private 등 접근제어지시자 마다 접근 할 수 있는 범위가 다르다

``` java
public class UseCalculater {
    public static void main(String[] args) {
        MyCalculater cal = new MyCalculater();
        cal.calculater(4, '+', 3); // 7
        cal.calculater(4, '-', 3); // 1
        cal.calculater(4, '*', 3); // 지원하지 않는 연산자
    }
}
```

protected : 상속하는 경우 부모클래스의 멤버와 메소드를 사용

default : 패키지 내부에서만 접근 허용

```
public > protected > default > private
```
이 순서로 접근이 제한된다

``` java
public class MyCalculater2 extends MyCalculater {
    public void calculate2(int a, String b, int c) {
        if (b == '+') {
            add(a, c); // 접근 불가
        } else if (b == '-') {
            minus(a, c); // 접근 불가
        } else {
            System.out.println("지원하지 않는 연산자")
        }
    }
}
```
위 코드는 MyCalculeter 클래스를 상속받아 그 메소드를 실행하려 하는 코드이다.

MyCalculter의 add와 minus는 private 메소드이므로 접근이 제한된다.

이 때 protected와 default 접근제어 지시자를 사용할 수 있다

``` java
public class MyCalculater {
    public void calculater(int a, char b, int c) {  // public (외부 접근 허용)
        if (b == '+') {
            add(a, c);
        } else if (b == '-') {
            minus(a, c);
        } else {
            System.out.println("지원하지 않는 연산자");
        }
    }

    protected void add(int a, int c) {  // protected (상속받은 클래스에서 접근 허용)
        System.out.println(a + c);
    }

    void minus(int a, int c) { // default (같은 패키지 내에서 접근 허용)
        System.out.println(a - c);
    }
}
```
접근제어 지시자를 수정한 코드이다

이것을 아까의 main에서 실행한다면
``` java
public class MyCalculater2 extends MyCalculater {
    public void calculate2(int a, String b, int c) {
        if (b == '+') {
            add(a, c); // 상속받은 클래스여서 접근 가능
        } else if (b == '-') {
            minus(a, c); // 같은 패키지여서 접근 가능
        } else {
            System.out.println("지원하지 않는 연산자");
        }
    }
}
```

클래스 자체에도 접근제어를 할 수 있다.

