# 0629_RegularExpression

## 정규 표현식

문자열에 특정한 규칙을 가진 문자열이 있는지 알아보기 위해 사용하는 표현 형태

예시)
``` java
^i\w*z$\s
```
위 코드는 i로 시작해서 z로 끝나는 단어를 나타내기 위한 정규 표현식이다.

```
^ : 라인의 시작
i : 문자 i
\w : 문자 또는 숫자
* : 0개 이상
z : 문자 z
$ : 라인 끝
\s : 공백문자
```
정규 표현식을 잘 다룰 줄 알게 되면 문자열을 잘 다룰 수 있다.

정규 표현식의 의미는 다음과 같다

```
. : 임의의 한 글자
* : * 바로 앞의 무자가 없거나 한 개 이상
+ : + 바로 앞의 문자가 최소 한 개 이상
? : ? 바로 앞의 문자가 없거나 한 개
^ : 줄의 시작
$ : 줄의 끝
[] : 두 문자 사이에 -를 써서 문자 범위 표현. [] 안에서 ^의 의미는 ^다음 문자 제외
| : or 연산자
\s : 공백
\S : 공백 제외
\w : 알파벳 또는 숫자
\W : 알파벳, 숫자 제외
\d : 숫자 
\D : 숫자 제외
(?!) : 앞 부분에 쓰면 대소문자 구별 x
\ : 특수문자 그대로 표현
```

## Matcher 클래스

패턴 매칭 메소드이다.

```
1. Pattern 생성 : Pattern p = Pattern.compile("정규식");
2. Matcher 생성 : Matcher m = p.matcher("정규식을 가지고 찾아볼 원본 문자열");
3. 정규식으로 문자열을 반복해서 찾는다 : while(m.find());
4. 찾은 문자열 위치는 m.start()에 담기고, m.group()엔 찾은 문자열이 담겨 있다
```

``` java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExpTest5 {
    public static void main(String[] args) {
        Pattern p = Pattern.compile("Java");
        Matcher m = p.matcher("My Java Application Java Program");

        while(m.find()) {
            System.out.println("Java 발견 위치 : " + m.start()); // 3, 20
        }

        String str1 = m.replaceAll("Test"); // Java를 모두 Test로 바꿈
        System.out.println(str1); // My Test Application Test Program
    }
}
```