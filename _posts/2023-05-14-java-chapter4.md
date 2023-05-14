---
title: java의 정석 4장, 조건문과 반복문
categories: [java]
comments: true
---

**조건문**

*if문*

만일 조건식이 참이라면 괄호 안의 문장들을 수행함

```java
if (score > 80) {
    System.out.println("합격입니다.");
}
```

*if-else문*

조건식의 결과가 참일 때는 if 블럭 안의 문장을 수행하고, 참이 아니라면 else 블럭싀 문장들을 수행함

```java
if (score > 80) {
    System.out.println("합격입니다.");
} else {
    System.out.println("불합격입니다.");
}
```

*switch문*

하나의 조건식으로 많은 경우의 수를 처리함

```java
switch (조건식) {
    case 값1 :
        수행될 문장
        break;
    case 값2 :
        수행될 문장
        break;
    case 값3 : 
        수행될 문장
        break;
    default : 
        수행될 문장
}
```
제약조건
1. switch문의 조건식 결과는 정수 또는 문자열이여야 한다.
2. case문의 값은 정수 상수(문자), 문자열만 가능하며 중복되지 않아야 한다.



**반복문**

*for문*

```java
for (초기화; 조건식; 증감식) {
    수행할 문장;
}
```

어떤 작업이 조건식에 맞는 동안 반복적으로 수행되도록 할 때 사용함

```java
for(int i = 0; i <= 5; i++) {
    System.out.println("I can do it!");
}
```



*while문*

