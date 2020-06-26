# 0626_Wrapper

## Wrapper 클래스

제네릭을 사용할 때 기본 자료형은 클래스가 아니어서 타입 지정 할 수 없다.

이를 해결하기 위해 자바에선 각 자료형에 해당하는 클래스를 만들어 준다. 이것이 Wrapper 클래스이다.

기본 자료형을 Wrapper 클래스로 바꾸거나, Wrapper 클래스를 기본 자료형으로 바꾸는 정도의 기능을 한다.

``` java
public class WrapperUse {
    int age = Integer.parseInt("35"); // 정수 문자열 정수변환
    double price = Double.parseDouble("20.3"); // 실수 문자열 실수변환

    Integer myAge = new Integer(35); // int Integer로 변환
    Integer myAge2 = new Integer("35"); // String Integer로 변환
}
```

## AutoBoxing

int와 Integer 변환을 할 때, Integer 생성자로 생성하지 않아도 알아서 클래스 생성을 해 준다.

``` java
public class AutoBoxingTest {
    public static void main(String[] args) {
        Integer myInt = 10; // 생성자로 생성하지 않아도 자동 생성 (AutoBoxing)
        int myNum = myInt; // myInt 객체 int에 바로 대입 (AutoUnboxing)

        int sum = myInt + myNum; // 둘 사이의 산술 연산도 가능
    }
}
```