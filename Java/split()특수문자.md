## split() 메소드

- Java에서 문자열을 특정 regex로 자를 때 사용한다.
- 특정 특수문자에서는 동작이 제한된다.
- 구분자들 사이에 ‘|’를 사용하면 여러 구분자들을 사용이 가능하다.

```java
String S = "1,2,3_4,5 6 7";
String[] res = S.split(",|_| ");

for (String s : res) {
	System.out.print(s);
}

// 출력값
1234567
```

- split() 메소드 이용시 특정 특수문자는 에러가 발생한다.
- split은 구분자를 정규표현식으로 받기 때문에 예약어로 사용한 특수문자는 그대로 사용할 수 없다.
- 예를 들면 |, ?, *, (, [, ^, & 등등..
- 사용하기 위해선 \\(백슬래시 두번)을 앞에 넣어 주어야 정상적으로 작동한다.

```java
String S = "1^2";
String[] res = S.split("\\^");

for (String s : res) {
	System.out.print(s);
}

// 출력값
12
```

- 참고로 \(백슬래시)를 문자열로 표현하기 위해선 “\\”로 표현해야한다.
- 그래서 split을 하기 위해선 “\\\\”를 사용해야 정상 작동한다.

```java
String S = "1\\2";
String[] res = S.split("\\\\");

for (String s : res) {
	System.out.print(s);
}

// 출력값
12
```
