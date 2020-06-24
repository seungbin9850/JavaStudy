# 0624_Collection

## 컬렉션 프레임워크

java.util 패키지 안에 있는 Collection 클래스

총 11가지의 자료구조들을 가져다 사용할 수 있음.

``` java
import java.util.ArrayList; // ArrayList 사용

public class ArrayListSample {
    public class void main(String[] args) {
        ArrayList<String> myStringArrays = new ArrayList<String>(); //String형

        myStringArrays.add("java1"); // add 메소드를 사용하여 값 추가 0번 index
        myStringArrays.add("java2"); // add 메소드를 사용하여 값 추가 1번 index
        myStringArrays.add("java3"); // add 메소드를 사용하여 값 추가 2번 index

        String myString1 = myStringArrays.get(1); // myStringArrays 배열 1번째 값 읽기
        System.out.println(myString1); // java2

        myStringArrays.add(1, "자바2"); // 1번째 값 수정
        String myString2 = myStringArrays.get(1);
        System.out.println(myString2); // 자바2

        myStringArrays.remove(0); // 배열 0번째 삭제
    }
}
```
ArrayList라는 클래스를 이용하여 그 클래스의 메소드를 사용한 코드이다.

add(), remove() 외에도

배열의 전체를 지우는 clear()

배열의 크기를 구하는 size()

배열이 비어있는지 확인하는 isEmpty() 등이 있다.

이런 메소드들은 부모클래스인 Collection 인터페이스의 메소드이다.

Collection을 구현한 다른 클래스들의 사용법도 같다고 보면 된다.

## Iterator

Java에서는 next() 메소드를 가지고 있는 반복 인터페이스인 Iterator라는 것이 있다.

``` java
import java.util.ArrayList; // ArrayList 사용
import java.util.Iterator; // Iterator 사용

public class ArrayListSample {
    public class void main(String[] args) {
        ArrayList<String> myStringArrays = new ArrayList<String>(); //String형

        myStringArrays.add("java1"); // add 메소드를 사용하여 값 추가 0번 index
        myStringArrays.add("java2"); // add 메소드를 사용하여 값 추가 1번 index
        myStringArrays.add("java3"); // add 메소드를 사용하여 값 추가 2번 index

        Iterator<String> myIterator = myStringArrays.iterator();
        while(myIterator.hasNext()) { // 다음 항목이 있는지
            String myString = myIterator.next(); // 다음 항목 읽어오기
            System.out.println(myString);
        }
    }
}
```