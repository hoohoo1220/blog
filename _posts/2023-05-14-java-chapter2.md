---
title: java의 정석 2장, 변수
categories: [java]
comments: true
---

**출력하기**
          
Java에서는 `System.out.println()` 함수를 사용하여 출력할 수 있다.

```java
System.out.println(3 + 5) : 계산되어 출력 -> 8
System.out.println("3 + 5") : 그대로 출력 -> 3 + 5
```
괄호 안에 숫자를 넣으면 계산된 결과가 출력되지만 큰따옴표 안에 넣은 내용은 그대로 출력된다.
(사칙연산 모두 동일)


```java
System.out.printf() : 줄바꿈 없이 그대로 출력
System.out.println() : 줄바꿈을 포함하여 출력
```
줄바꿈을 하지 않으면 이전에 출력돈 내용 바로 뒤에 출력된다.



**변수의 선언과 저장**

변수란? 하나의 값을 저장할 수 있는 저장공간

선언 방법 -> 변수타입 변수이름;
ex) `int x;`

```java
int a;
long b;
float c;
double d;
char e;
String g;
```



**상수와 리터럴**

1. 상수

상수 선언 방법 -> final
상수 : 저장 후 변경 불가능

```java
final int MAX_SPEED = 10;
MAX_SPEED = 100;
```
이름은 모두 대문자로 하는 것이 관례, 여러 단어 사용시 '_' 사용

2. 리터럴 (literal)
우리가 기존에 알고 있던 상수의 다른 이름

int 10; 에서 10을 literal 이라고 부름



**입력받기**

Scanner 클래스 객체 생성
```java
Scanner scanner = new Scanner(System.in);

String input = scanner.nextLine();
int num = scanner.nextInt();
```


**오버플로우**

오버플로우(overflow)란?
 : 연산 과정에서 해당 타입이 표현할 수 있는 값의 범위를 넘어서는 것