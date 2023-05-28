---
title: java의 class
categories: [java]
comments: true
---

**클래스**

클래스란?  객체를 정의해 놓은 것, 객체의 설계도 또는 틀
클래스의 용도 : 객체를 생성하는데 사용


객체란? 실제로 존재하는 것, 사물 또는 개념
객체의 용도 : 객체가 가지고 있는 기능과 속성에 따라 다름  

ex) 책상, 의자 등 사물, 개념, 논리 등 무형적인 것들


객체의 구성요소

속성 -> 멤버변수
기능 -> 메서드

ex) TV 클래스

```java
class Tv {
    String color;   // 멤버변수
    boolean power;
    int chanel;

    void power() {  // 메서드
        power = !power;
    }
    void channelUp() {
        channel++;
    }
    void channelDown() {
        channel--;
    }
}
```



*객체와 인스턴스*

클래스로부터 객체를 만드는 과정을 클래스의 인스턴스화라고 함.
클래스로부터 만들어진 객체를 그 클래스의 인스턴스라고 함.

`클래스 ---(인스턴스화)--> 인스턴스(객체)`



*한 파일에 여러 클래스 작성하기*

소스파일의 이름은 public class의 이름과 일치해야 함.
public class가 없다면, 소스파일 내의 어떤 클래스의 이름으로 해도 상관없음.

```java
올바른 작성
//Hello2.java
public class Hello2 { }
       class Hello3 { }

//Hello2.java
class Hello2 { }
class Hello3 { }


잘못된 작성
//Hello2.java
public class Hello2 { }
public class Hello3 { }

//Hello3.java
public class Hello2 { }
       class Hello3 { }

//hello2.java
public class Hello2 { }
       class Hello3 { }
```



*객체의 생성과 사용*

클래스를 선언한 것은 설계도를 작성한 것에 불과하므로, 인스턴스르르 생성해야 제품을 사용할 수 있음.

```java
일반적인 인스턴스 생성 방법

클래스명 변수명;
변수명 = new 클래스명();

Tv = t;
t = new Tv();
```



**클래스의 정의**

*데이터와 함수의 결합*

변수 : 하나의 데이터를 저장할 수 있는 공간
배열 : 같은 종류의 여러 데이터를 하나의 집합으로 저장할 수 있는 공간
구조체 : 서로 관련된 여러 데이터를 종류에 관계없이 하나의 집합으로 저장할 수 있는 공간
클래스 : 데이터와 함수의 결합 (구조체 + 함수)



*사용자 정의 타입*

기본 자료형 이외에 프로그래머가 서로 관련된 변수들을 묶어서 하나의 타입으로 새로 추가하는 것을 '사용자 정의 타입'이라고 함.

```java
시간 표현
int hour;
int minute;
float second;
```

위와 같은 방식으로 코드를 작성하면 표현하려는 시간의 수가 많아질수록 사용해야 할 변수들의 수가 많아지기 때문에,
시, 분, 초를 하나로 묶는 사용자 정의 타입, 클래스를 정의하여 사용함.

```java
class Time {
    int hour;
    int minute;
    float second;
}

Time t1 = new Time();
Time t2 = new Time();

Time[] t = new Time[3];
t[0] = new Time();
```



*선언 위치에 따른 변수의 종류*

멤버변수를 제외한 나머지 변수들은 모두 지역변수,
멤버변수 중 static이 붙은 것은 클래스 변수, 붙지 않은 것은 인스턴스 변수임.

```java
class Variables {
    int iv;     // 클래스 영역
    static int cv;

    void method() {
        int lv = 0;     // 메서드 영역
    }
}
```

*변수의 종류    선언 위치       생성시기*

클래스 변수     클래스 영역     클래스가 메모리에 올라갈 때

인스턴스 변수   클래스 영역     인스턴스가 생성되었을 때

지역변수    클래스 영역 이외의 영역     변수 선언문이 수행되었을 때



*클래스 변수와 인스턴스 변수*

예시) 카드

```java
class Card {
    String kind;    // 인스턴스 변수
    int number;

    static int width = 100;     // 클래스 변수
    static int height = 250;
}
```

인스턴트 변수는 각기 다른 값을 유지할 수 있지만, 
클래스 변수는 모든 인스턴스가 하나의 저장공간을 공유하므로 항상 공통된 값을 가짐.



**메서드**

메서드란? 특정 작업을 수행하는 일련의 문장들을 하나로 묶은 것

메서드는 크게 '선언부'와 '구현부'로 이루어져 있다.