# 0630_InnerClass

## 중첩 클래스

클래스나 인터페이스 내부에 정의되어 있는 클래스

안쪽 클래스에서 바깥쪽 클래스의 모든 멤버변수와 메소드에 접근 가능

```
1. 인스턴스 클래스 (instance class)
   외부 클래스의ㅡ 멤버변수 선언 위치에서 선언됨

2. 스태틱 클래스 (static class)
   외부클래스의 멤버변수 선언 위치에서 선언됨. 외부클래스의 주로 static 메소드에서 사용됨

3. 지역 클래스 (local class)
   외부클래스의 메소드나 초기화 블록안에 선언되어 선언된 영역 내부에서만 사용됨

4. 익명 클래스 (annonymous class)
   클래스의 선언과 객체의 생성을 동시에 하는 이름없는 클래스. 일회용으로 사용됨
```

## 인스턴스 클래스

통상적인 멤버 변수와 동일하게 사용 가능

static 멤버나 static 메소드를 선언할 수 없다

``` java
public class OuterClass {
    int num;

    class InnerClass {
        public void method() {
            System.out.println(num);
        }
    }
}

// main
public class InnerClassTest {
    public static void main(String[] args) {
        OuterClass oc = new OuterClass();
        OuterClass.InnerClass ic = oc.new InnerClass();
        ic.method();
    }
}
```
외부 클래스를 먼저 생성하고 나서 그 인스턴스를 갖고 내부클래스를 선언하여야 한다

## 스태틱 클래스

통상적인 static 멤버변수와 동일하게 사용 가능

외부클래스의 static 멤버변수만 접근 가능

static 멤버를 선언할 수 있고, static 메소드를 선언할 수 있음

``` java
public class OuterClass {
    static int num;

    static class InnerClass {
        public void method() {
            System.out.println(num); // static 변수만 접근 가능
        }
    }
}

// main
public class InnerClassTest {
    public static void main(String[] args) {
        OuterClass.InnerClass ic = new OuterClass.InnerClass();
        ic.method();
    }
}
```
static 클래스이므로 외부 클래스 생성이 필요 없다

## 로컬 클래스

외부클래스의 메소드 내에 존재하는 클래스

메소드 내부에서만 사용되고 메소드가 종료되면 사라지는 클래스

static 멤버나 static 메소드를 선언할 수 없다

``` java
public class OuterClass {
    static int num;

    public void method(final int paraNum, int paraNum2) { 
        // final인 인자만 로컬클래스에 접근 가능
        final int localNum = 0;
        int localNum2 = 0;

        class InnerClass {
            int innerNum;

            public void innerMethod() {
                System.out.println("외부클래스 멤버 : " + num);
                System.out.println("로컬클래스 멤버 : " + innerNum);
                System.out.println("메소드 final 변수 : " + localNum);
                System.out.println("메소드 final 인자 : " + paraNum);
            }
        }
        // 메소드 내부에서 생성해서 바로 사용해야 함
        InnerClass ic = new InnerClass();
        ic.innerMethod();
    }
}

// main
public class InnerClassTest {
    public static void main(String[] args) {
        OuterClass oc = new OuterClass();
        oc.method(10, 20);
    }
}
```

## 익명 클래스

메소드 내에 존재하는 로컬클래스의 특별한 형태

기존 클래스나 인터페이스의 특정 메소드를 오버라이딩하여 원하는 형태로 재정의 하여 사용

지역변수는 final만 가능

``` java
new 상위클래스명() {
    오버라이딩할 메소드() {
        메소드 재정의;
    }
}
```
위의 형태로 선언함

``` java
public class OuterClass {
    public static void main(String[] args) {
        // 익명클래스 선언과 생성을 동시에
        Runnable runnable = new Runnable() {
            @Override
            public void run() {
                System.out.println("별도 스레드에서 프린트");
            }
        };
        Thread t = new Tread(runnable); // 생성된 익명클래스 인스턴스 사용
        t.start();
    }
}
```