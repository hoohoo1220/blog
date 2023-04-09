---
title: java 문법 정리
categories: [java]
comments: true
---

자바의 시작 : 메인 함수



1. 자바의 기본 자료형

쓸 수 있는 크기가 다르다

자바의 기본 자료형은 다음과 같다 :

기본형 (primitive type)

정수형

- `byte`: 8비트 정수 (-128 ~ 127)
- `short`: 16비트 정수 (-32,768 ~ 32,767)
- `int`: 32비트 정수 (-2,147,483,648 ~ 2,147,483,647)
- `long`: 64비트 정수 (-9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807)

실수형

- `float`: 32비트 실수
- `double`: 64비트 실수

boolean형

- `boolean`: true 또는 false

문자형

- `char`: 16비트 유니코드 문자

참조형 (reference type)

- String str = “Hello, world”;

사용자 정의 타입




2. 자바의 출력문

이 자료형들을 사용하여 변수를 선언하고 값을 할당할 수 있다.

Java에서는 `System.out.println()` 함수를 사용하여 출력할 수 있다.

```java
System.out.print() : 줄바꿈 없이 그대로 출력
System.out.println() : 줄바꿈을 포함하여 출력
```

예시:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```




3. 자바의 입력문

Java에서 `Scanner` 클래스를 사용하여 입력을 받을 수 있다.

```java
Scanner InputN = new Scanner(System.in);
System.out.println("나이를 입력하세요.");
//정수 입력
int InputAge = InputN.nextInt();
System.out.println("입력된 나이는 : " + InputAge);

Scanner InputS = new Scanner(System.in);
System.out.println(("문자열을 입력해주세요."));
//문자열 입력
String InputStr = InputS.nextLine();
System.out.println("입력된 문자열은 : " + InputStr);
```

예시:

```java
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("이름을 입력하세요 : ");
        String name = scanner.next();
        System.out.println(name + "님, 안녕하세요!");
        scanner.close();
    }
}
```




4. 자바의 조건문

Java에서 조건문을 사용하는 방법은 다음과 같다 :

`if` 문 :

```java
if (조건식) {
    // 조건식이 참일 때 실행되는 코드
}
```

예시:

```java
public class Lecture03 {
    public static void main(String[] args) {
        //조건문

        int number = 4;
        if (number == 4) {
            System.out.println("number을 출력 : " + number);
        } else {
            System.out.println(" ㅜㅜㅜㅜ ");
        }
    }
}
```




5. 자바의 반복문

Java에서는 다음과 같은 반복문을 사용할 수 있다 :

`for`문 :

```java
for (초기화식; 조건식; 증감식) {
    // 코드 블록
}
```

예시:

```java
public class Lecture04 {
    public static void main(String[] args) {
        //반복문
        for (int i = 0; i < 100; i++) {
            if (i%2 == 0) {
                System.out.println(i);
            }
        }
    }
}
```




6. 수도코드

수도코드란, 알고리즘이나 프로그램의 논리 구조를 설명하기 위해 사용되는 비공식적인 프로그래밍 언어이다. 수도코드는 실제 프로그램을 작성하기 전에 알고리즘을 설계하여 정리할 수 있는 언어이다.

예시 :

```java
1부터 100까지 짝수의 합 의사코드

1. 변수 i, 합 sum를 선언한다. sum은 0으로 초기화한다.
2. i를 1부터 100까지 반복문을 돌린다.
3. i를 2로 나눈 나머지가 0이면, i를 sum에 더한다.
4. 3번으로 돌아간다.
5. for문이 종료되면 프로그램을 종료한다.
```

실제 코딩 :

```java
public class Lecture01 {
    public static void main(String[] args) {
        int i, j;
        for (i = 1; i <= 9; i++)
            for (j = 1; j <= 9; j++)
            {
                System.out.print(i + " * " + j + " = " + i*j + "\t");
                if (j % 9 == 0) {
                    System.out.println("");
                }
            }
    }
}
```




7. 자바의 배열

Java에서 배열을 사용하는 방법은 다음과 같다.

```java
// 배열 생성 방법 1
int[] array1 = new int[5];
array1[0] = 10;
array1[1] = 20;
array1[2] = 30;
array1[3] = 40;
array1[4] = 50;

// 배열 생성 방법 2
int[] array2 = { 10, 20, 30, 40, 50 };

// 배열 생성 방법 3
int[] array3 = new int[] { 10, 20, 30, 40, 50 };

// 배열 출력
System.out.println("array1:");
for (int i = 0; i < array1.length; i++) {
    System.out.println(array1[i]);
}

System.out.println("array2:");
for (int i = 0; i < array2.length; i++) {
    System.out.println(array2[i]);
}

System.out.println("array3:");
for (int i = 0; i < array3.length; i++) {
    System.out.println(array3[i]);
}

```

예시:

```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = { 1, 2, 3, 4, 5 };
        int sum = 0;
        for (int i = 0; i < numbers.length; i++) {
            sum += numbers[i];
        }
        System.out.println("합계 : " + sum);
    }
}

```




8. 자바의 무작위 함수

무작위 함수는 Random 함수를 사용하여 선언할 수 있다.

```java
public class Random {
    public static void main(String[] args) {
        int randomNumber = (int) (Math.random() * 6); //0부터 5까지
        System.out.println(randomNumber);
    }
}
```