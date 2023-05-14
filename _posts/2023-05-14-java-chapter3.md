---
title: java의 정석 2장, 연산자
categories: [java]
comments: true
---

**연산자**
 : 연산을 수행하는 기구

 산술 ->   +, -, *, /, %, <<, >> 
 비교 ->   <, >, >=, <=, ==, !=
 논리 ->   &&, ||, !, &, |, ^, ~
 대입 ->   =
  + 기타 -> 형변환, 삼항, instanceof 등
 
 순서 : 산술 -> 비교 -> 논리 -> 대입

 

 **증감 연산자(++, --)**

 전위형 : 값이 참조되기 전에 증감
 ex) j = ++i;

 후위형 : 값이 참조된 후에 증감
 ex) j = i++;



 **형변환 연산자**

 변수 또는 상수의 타입을 다른 타입으로 변환하는 것

 (타입) 피연산자;

```java
double d = 85.4;
int score = (int)d;
```


**자동 형변환**
 : 기존의 값을 최대한 보존할 수 있는 타입으로 자동 형변환된다.