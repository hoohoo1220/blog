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






**임의의 정수 만들기**

난수(임의의 수)를 얻기 위해서는 `Math.random()`을 사용한다.

```java
0.0  <=  Math.random()  <  1.0     // 0.0과 1.0 사이의 범위에 속하는 하나의 double값 반환

(int)(Math.random() * 3)    // 1부터 3까지의 정수중 하나 반환
```






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

while문은 먼저 조건식을 평가하여 조건식이 거짓이면 문장 전체를 벗어나고,
참이면 { } 내의 문장을 수행하고 다시 조건식으로 돌아감.
조건식이 거짓이 될 때까지 이 과정 반복.

```java
int i = 1;
while (i <= 10) {
    System.out.println(i);
    i++;
}
```



*do-while문*

기본적인 구조는 while문과 같으나 조건식의 블럭의 순서를 바꾼 것

```java
do {
    // 조건식의 연산결과가 참일 때 수행될 문장들(처음 한번은 무조건 실행)
} while (조건식);
```



*break문*

break문은 자신이 포함된 가장 가까운 반복문을 벗어남.
if문과 함께 사용될 때, 특정 조건을 만족하면 반복문을 벗어나게 함.

```java
int sum = 0, i = 0;

while (true) {
    if (sum > 100) {
        break;
    }
    ++i;
    sum += i;
}
```



*continue문*

반복문 내에서만 사용될 수 있으며, 반복이 진행되는 도중에 만날 경우 반복문의 끝으로 이동하여 다음 반복으로 넘어감.
for문인 경우 증감식으로, while, d0-while문일 경우 조건식으로 이동함.

```java
for (int i = 0; i <= 10; i++) {
    if (i % 3 == 0) {
        continue;
    }
    System.out.println(i);
}
```



*이름이 붙은 반복문*

break문은 근접한 단 하나의 반복문만 벗어날 수 있음.
여러 개의 반복문이 중첩된 경우는 break문으로 벗어날 수 없음.
이때, 중첩 반복문 앞에 이름을 붙여 하나 이상의 반복문을 벗어나거나 건너뛸 수 있다.

```java
Loop1 : for(int i = 2; i <= 9; i++) {
    for (int j = 1; j <= 9; j++) {
        if (j == 5) {
            break Loop1;
        }
        System.out.println(i + " * " + j + " = " + i * j);
    }
    System.out.println();
}

/* 결과
2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
*/
```