---
title: java의 정석 5장, 배열
categories: [java]
comments: true
---

**배열**

배열이란?  '같은 타입'의 여러 변수를 하나의 묶음으로 다루는 것

```java
int score1, score2, score3, score4, score5;

int[] score = new int[5];

// 같은 결과를 내지만 수가 많을수록 배열이 훨씬 간단하다.
```



*배열의 선언과 생성*

`타입[] 변수이름;` 또는 `타입 변수이름[];`

배열을 선언하기만 하면 안됨.
배열을 생성해야만 비로소 값을 저장할 수 있기 때문.

```java
int[] score;    // 배열의 선언
score = new int[5];     // 배열의 생성

int[] arr = new int[10];    // 배열의 선언과 동시에 생성
```



*배열의 인덱스*

생성된 배열의 각 저장공간을 요소라 하며, `배열이름[인덱스]`의 형식으로 접근함.
인덱스는 배열의 요소마다 붙여진 일련번호로 각 요소 구별에 사용.

* 단 인덱스는 1이 아닌 0부터 시작.
* 인덱스의 범위는 0부터 '배열길이 -1'까지

```java
int score = new int[5];

score[3] = 100;
```



*배열의 길이*

배열이름.length를 통해 배열의 길이에 대한 정보를 얻을 수 있음.

```java
int[] arr = new int[5];

int tmp = arr.length;   // tmp = 5
```



**배열의 활용**

*총합과 평균*

배열의 모든 요소를 더해서 총합과 평균을 구함.

```java
int sum = 0;
float average = 0f;

int[] score = { 100, 88, 100, 100, 90 };

for (int i = 0; i < score.length; i++) {
    sum += score[i];
}
average = sum / (float)score.length;

System.out.println("총합 : " + sum);
System.out.println("평균 : " + average);
```



*최대값과 최소값*

```java
int[] score = { 79, 88, 91, 33, 100, 55, 95 };

int max = score[0];
int min = score[0];

for (int i = 1; i < score.lenght; i++) {
    if (score[i] > max) {
        max = score[i];
    } else if (score[i] < min) {
        min = score[i];
    }
}

System.out.println("최대값 : " + max);
System.out.println("최소값 : " + min);
```



*섞기(shuffle)*

배열 생성 후, random() 함수를 이용하여 무작위로 섞는 것

```java
int[] numArr = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
System.out.println(Arrays.toString(numArr));

for (int i = 0; i < 100; i++) {
    int n = (int)(Math.random() * 10);
    int tmp = numArr[0];
    numArr[0] = numArr[n];
    numArr[n] = tmp;
}
System.out.println(Arrays.toString(numArr));
```



**String배열**

*String배열의 선언과 생성*

배열의 타입이 String인 경우에도 int 배열과 선언과 생성 방법은 다르지 않음.

```java
String[] name = new String[3];

name[0] = "Kim";    // 초기화
name[1] = "Park";
name[2] = "Yi";
```



**커맨드 라인**

```java
c:\jdk1.8\work\ch5>java MainTest abc 123
```