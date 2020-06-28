# 0628_String

## 문자열 변환

문자열 2개 더하기

``` java
String str = "Hello" + "World!";
String str1 = "Hello".concat("World");
```

문자열 위치 바꾸기

``` java
String str = "Hello World!".replace("d", "D"); // Hello WorlD!
String str1 = "Hello World!".replace("l", "L"); // HeLLo WorLd!
String str2 = "Hello World!".replaceFirst("l", "L"); // HeLlo World!
```

특정 위치 문자 가져오기

``` java
char ch = "Hello World!".charAt(4); // o
String str = "Hello World".substring(3, 7); // lo W
```

대소문자 변경

``` java
String str = "Hello World!".toLowerCase(); // hello world!
String str1 = "Hello World!".toUpperCase(); // HELLO WORLD!
```

문자열 앞뒤 공백 제거

``` java
String str = "     Hello World!  ".trim(); // Hello World!
```

문자열 나누기

``` java
String str = "Hello World!";
String[] str1 = str.split(" "); // 공백 기준 문자열 나누기
System.out.println(str1[0]); // Hello 
System.out.println(str1[1]); // World!
```

## 문자 위치 검색

``` java
String str = "Hello World";

boolean isTrue = str.startsWith("He"); // He로 시작하는 문자열인지 (true)
boolean isTrue2 = str.endsWith("d"); // d로 끝나는 문자열인지 (true)
boolean isTrue3 = str.equals("Hello World!"); // 문자열 비교는 equals로

boolean isContain = str.contains("llo"); // llo를 포함하고 있는지 (true)

int index = str.indexOf("W"); // W의 위치 (7번째 이므로 6 반환)
int index2 = str.lastIndexOf("l"); // 마지막 l의 위치 (11번째 l)

int length = str.length(); // 문자열 길이 (12 반환)
```