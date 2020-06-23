# 0623_Final

## final

멤버변수, 메소드, class명 앞에 사용할 수 있다.

더 이상 바꿀 수 없는 값이라고 컴파일러에게 알려주는 것 (상수)

값을 초기화 하려면 선언 할 때 초기화 하는 방법과 생성자에서 초기화하는 방법이 있다.

``` java
class Test {
    final double PI = 3.14;
    final double PIP;

    public Test(adouble value) {
        PIP = value;
    }
}
```
이렇게 쓴다면 오류가 발생하지 않을 것이다.

하지만, PIP라는 변수는 인스턴스마다 다른 값이 들어가게 될 것이다.

그러면, 상수가 아니게 되므로 final을 사용할 필요가 없어지게 된다.

그래서 상수는 인스턴스에 따라 달라지지 않도록 static과 같이 쓴다.

``` java
static final double PI = 3.14;
```
메소드 앞에 final을 썼을 경우

부모클래스에서 정의한 메소드를 자식클래스에서 오버라이딩 할 수 없다.

클래스 명에 final을 붙인다면

클래스 전체를 바꿀 수 없게 한다.

상속도 불가능하고, 만들어진 클래스를 변경 없이 그대로 쓰는 것이다.

final 클래스 안의 method들은 final이라고 메소드명 앞에 적어두지 않아도 final 메소드가 된다.