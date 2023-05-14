---
title: java의 정석 4장, 조건문과 반복문
categories: [java]
comments: true
---

**조건문**

if문

```java
if (score > 80) {
    System.out.println("합격입니다.");
}
```

if-else문

```java
if (score > 80) {
    System.out.println("합격입니다.");
} else {
    System.out.println("불합격입니다.");
}
```

switch문

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