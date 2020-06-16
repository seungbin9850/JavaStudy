# 0616_Class

## 객체지향

객체라는 작은 단위로 프로그래밍을 한다는 것. (클래스 단위 프로그램)

클래스 : 멤버 변수와 메소드를 가진 하나의 덩어리

객체지향이 필요한 이유

- 클래스의 멤버변수는 클래스 내의 메소드에서만 값을 읽고 수정할 수 있음

- 특정 클래스는 비슷한 일을 처리하는 메소드들의 집합체

- 클래스들을 합치게 되면, 서로 간섭하지 않고 프로그램이 잘 완성됨

## 클래스

``` java
public class Student {
    String name;
    double gpa;

    public String getName() {
        return name;
    }

    public void setGpa() {
        gpa = 4.3;
    }
}
```

위는 두 개의 멤버 변수와 두 개의 메소드를 가진 클래스를 선언한 것이다.

## 생성자

선언된 클래스를 사용하려면 생성자를 호출해야 한다.

생성자를 호출하면 클래스의 인스턴스 변수를 가지고 메소드를 호출할 수 있다.

``` java
Student std = new Student(); // 생성자
std.getName(); // 메소드 호출
```

생성자는 우리가 직접 정의하지 않아도 Java 컴파일러가 생성자를 만들어준다.

``` java
public class Student {
    String name;
    double gpa;

    public Student() { // 생성자
        name = "홍길동";
        gpa = 4.3;
    }

    public String getName() {
        return name;
    }

    public void setGpa() {
        gpa = 4.3;
    }
}
```

위처럼 Student() 생성자를 명시적으로 선언할 수도 있다.

``` java
public class Student {
    String name;
    double gpa;

    public Student(String pName, double pGpa) { // 생성자
        name = pName;
        gpa = pGpa;
    }

    public String getName() {
        return name;
    }

    public void setGpa() {
        gpa = 4.3;
    }
}

...

Student std = new Student("홍길동", 4.3);
```

위처럼 파라미터가 있는 생성자를 호출할 수도 있다.

이 땐 자바 컴파일러가 생성자를 추가해주지 않는다.