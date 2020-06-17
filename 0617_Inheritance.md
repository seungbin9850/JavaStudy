# 0617_Inheritance

## 상속

자바의 클래스는 기존 클래스를 이용하여 기능이 추가된 클래스를 만들어 사용할 수 있음.

부모 클래스의 기능을 상속 (메소드 등)해서 자식 클래스를 만듦.

자식 클래스에 부모 클래스의 기능을 확장해서 사용할 수 있음.

상속은 extends 키워드를 사용하여 할 수 있음

``` java
class AddCalculater {
    int a;
    int b;

    public AddCalculater(int pa, int pb) {
        a = pa;
        b = pb;
    }

    public void add() {
        System.out.println(a + b);
    }
}

class MinusCalculater extends AddCalculater { // AddCalculater 클래스 상속
    public MinusCalculater(int pa, int pb) {
        super(pa, pb); // super : 부모 클래스의 생성자를 호출
    }

    public void minus() {
        System.out.println(a - b);
    }
}
```

위 코드는 MinusCalculater 클래스가 AddCalculater 클래스를 상속받는 코드이다.

``` java
public class JavaStudy {
    public static void main(String[] args) {
        MinusCalculater cal = new MinusCalculater(10, 5); // MinusCalculater 생성자

        cal.add(); // 15
        cal.minus(); // 5
    }
}
```

MinusCalculater 클래스엔 add 메소드가 없다.

그런데도 add 메소드를 사용할 수 있는 이유는 AddCalculater 클래스를 상속받았기 때문이다.