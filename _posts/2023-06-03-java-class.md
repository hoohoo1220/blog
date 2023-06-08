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

메서드는 크게 '선언부'와 '구현부'로 이루어져 있음.
메서드를 정의한다는 것은 선언부와 구현부를 작성한다는 것

```java
반환타입 메서드이름 (타입 변수명, 타입 변수병, ...)
{
    // 메서드 호출 시 시행될 코드
}

int add(int a, int b)
{
    int result = a + b;
    return result;
}
```



**메서드의 선언부**

메서드 선언부는 "메서드의 이름", "매개변수 선언", "반환타입"으로 구성됨.


*매개변수 선언*

매개변수는 메서드가 작업을 수행하는데 필요한 값을 제공받기 위한 것,
필요한 값의 개수만큼 변수 선언

* 두 변수의 타입이 같아도 변수의 타입 생략 불가능
```java
int add(int x, y) // 에러

int add(int a, int b) // OK
```


*반환타입*

메서드의 작업수행 결과인 '반환값'의 타입을 적는다.

* 반환값이 없는 경우 반환타입으로 'void'를 적어야 함.

```java
void print99danAll() {
    for (int i = 1; i <= 9; i++) {
        for (int j = 2; j <= 9; j++) {
            System.out.println(j + "*" + i + "=" + (j * i) + "  ");
        }
    }
}
```



**메서드의 구현부**

메서드의 선언부 다음에 오는 괄호 {}를 '메소드의 구현부'하고 함
이곳에 메서드를 호출했을 때, 수행될 문장들을 넣음.

*return문*

메서드의 반환타입이 'void'가 아닌 경우, 구현부 {} 안에 'return 반환값;'이 반드시 포함됨.
반환타입이 'void'인 경우 컴파일러에서 자동으로 'return;'을 추가해주었기 떄문.

```java
int add(int x, int y) {
    int result = x + y;
    return result;
}
```


*지역변수*

메서드 내에서 선언된 변수를 지역변수라고 함.

```java
int add(int x, int y) {
    int result = x + y;
    return result;
}


int multifly(int x, int y) {
    int result = x * y;
    return result;
}
```



**메서드의 호출**

메서드를 호출해야만 구현부 {}의 문장들이 수행된다.

```java
메서드 이름(값1, 값2, ...);

print99danAll();
int result = add(3, 5);
```



*인수와 매개변수*

메서드를 호출할 때, () 안에 지정해준 값들을 '인수'라고 함.
* 인수의 타입은 매개변수와 일치하거나 자동 형변환이 가능한 것이어야 함.



*static 메서드와 인스턴스 메서드*

static을 붙이는 경우 (static 메서드)

1. 클래스를 설계할 때, 멤버변수 중 모든 인스턴스에 공통으로 사용하는 것

2. 클래스 변수는 인스턴스를 생성하지 않아도 사용할 수 있다.

3. 클래스 메서드는 인스턴스 변수를 사용할 수 없다.

4. 메서드 내에서 인스턴스 변스를 사용하지 않는다면 static을 붙이는 것을 고려한다.


* 클래스의 멥버면수 중 모든 인스턴스에 공통된 값을 유지해야 하는 것이 있는지 살펴보고 있으면, static을 붙여준다.

* 작성한 메서드 중 인스턴스 변수나 인스턴스 메서드를 사용하지 않는 메서드에 static을 붙일 것을 고려한다.



**생성자**

생성자는 인스턴스가 생성될 때 호출되는 '인스턴스 초기화 메서드'이다.

인스턴스 변수 초기화 작업에 주로 사용되며, 인스턴스 생성 시에 실행되어야 하는 작업을 위해서도 사용된다.


조건
1. 생성자의 이름은 클래스의 이름과 같아야 한다.

2. 생성자는 리턴 값이 없다.


```java
클래스이름( 타입 변수명, 타입 변수명, ...) {
    // 인스턴스 생성 시 수행될 코드,
    // 주로 인스턴스 변수의 초기화 코드를 적는다.
}

class Point {
    Point() {   // 매개변수가 없는 생성자
        ...
    }

    Point(int x, int y) {   // 매개변수가 있는 생성자
        ...
    }
    ...
}
```


*기본 생성자*

```java
클래스이름() {} // 기본 생성자

Point() {}  // Point클래스의 기본 생성자
```


*매개변수가 있는 생성자*

생성자도 메서드처럼 매개변수를 선언하여 호출 시 값을 넘겨받아 인스턴스의 초기화 작업에 사용할 수 있다.

```java
Car() {}    // 기본 생성자
Car(String c, String g, int d) {    // 생성자
    color = c;
    gearType = g;
    door = d;
}
```

매개변수가 있는 생성자를 사용하면 코드를 간결하고 직관적으로 만들 수 있다.

```java
Car c = new Car();
c.color = "white";
c.gearType = "auto";
c.door = 4;

|
V

Car c = new Car("white", "auto", 4);
```



**생성자에서 다른 생성자 호출하기 - this()**

같은 클래스 멤버 간 서로 호출할 수 있는 것처럼 생성자 간에도 서로 호출이 가능함.

조건
* 생성자의 이름으로 클래스이름 대신 this를 사용한다.

* 한 생성자에서 다른 생성자를 호출할 때는 반드시 첫 줄에서만 호출이 가능하다.

```java
Car(String c, String g, int d) {
    color = c;
    gearType = g;
    door = d;
}

|
V

Car (String color, String gearType, int door) {
    this.color = color;
    this.gearType = gearType;
    this.door = door;
}
```

*this*  인스턴스 자신을 가리키는 참조변수, 인스턴스의 주소가 저장되어 있다.
        모든 인스턴스메서드에 지역변수로 숨겨진 채 존재한다.

*this(), this(매개변수)*  생성자, 같은 클래스의 다른 생성자를 호출할 때 사용한다.
매개변수