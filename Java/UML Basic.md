# UML 기초

## UML 이란?
* 모델링을 위해 시스템을 모델로 표현해주는 언어
* 시스템 개발 과정에서 개발자 사이의 의사 소통이 원할하게 이루어지도록  표준화한 통합 모델링
* UML 2.0에서는 시스템의 구조(Structure)와 동작(Behavior)을 표현하는 13가지 다이어그램을 제공

### 클래스 다이어그램
* 시간에 따라 변하지 않는 시스템의 정적인 면을 보여주는 대표적인 UML 구조 다이어그램
* 시스템을 구성하는 클래스와 그들 사이의 관계를 보여줌
* 주요 구성 요소는 클래스와 관계

#### 클래스
* 동일한 속성과 행위를 수행하는 객체의 집합
	> 컴공 1234 학번 3학년  철수와 컴공 3456 학번 4학년 영희는 하나의 객체로 여길수 있고, 학생이라는 집합이나 래스의 인스턴스로도 생각할수 있다.
* 객체를 생성하는 설계도
```java
public class Cat {
    private String name;
    
    public void meow() {
        System.out.println(name + "~~~~~~" + "웁니다");
    }
    
    public Cat(String name) {
    	this.name = name;
    }
}
```

위 코드에서 Cat 클래스를 고양이를 만들어내는 설계도라고 생각하면 이 설계도로부터 실제 고양이를 만들려면 new  연산자를 사용하면 된다.
	
```java
Cat cat1 = new Cat("치즈");
Cat cat2 = new Cat("람다");
```

UML에서는 다음과 같은 박스로 클래스를 표현한다.
<p align="center">
    <img src="http://www.plantuml.com/plantuml/png/SoWkIImgAStDuIhEpimhI2nAp5L8paaiBdOiAIdAJ2ejIVLCpiyBpgnALJ3W0aieE2UMA5HpAUZc9UQcSYbevwRcbsjeSjLoEQJcfG0D0W00" />
</p>

가장 윗부분은 클래스 이름, 중간 부분에는 클래스의 특징을 나타내는 속성을, 마지박 부분에는 클래스가 수행하는 책임, 즉 연산들을 기술한다.

클래스의 속성과 연산을 기술할때 앞의 부호를 붙이는 데 이는 속성과 연산의 가시화를 정의한것이다.

|접근 제어자|표시|설명|
|:----|:----:|:----|
|public|+|어떤 클래스의 객체에서든 접근 가능|
|private|-|이 클래스에서 생성된 객체들만 접근 가능|
|protected|#|이 클래스와 동일 패키지에 있거나 상속 관계에 있는 하위 클래스의 객체들만 접근 가능|
|package|~|동일 패키지에 있는 클래스의 객체들만 접근 가능|

* 분석 단계의 클래스
  * 속성의 구체적인 타입 정보나 가시화 정보보다 어떤 것을 속성으로 하는지가 더 중요
* 설계 단계의 클래스
  * 바로 코드를 생성이 가능할 수 있는 겅도로 구체적인 타입 정보와 가시화 정보를 기술

||표기 방법|
|:----|:----|
|속성 | [+\|-\|#\|~]이름: 타입[다중성 정보][=초기값]|
|연산 | [+\|-\|#\|~]이름(인자1: 타입1, ... , 인자n:타입n):반환 타입|
>'[ ]'부분은 생략할 수 있는 항목이다.

<p align="center">
  분석단계의 클래스(좌) 설계 단계의 클래스(우) 
</p>

<p align="center">
    <img src="http://www.plantuml.com/plantuml/png/SoWkIImgAStDuIhEpimhI2nAp5L8paaiBdOiAIdAJ2ejIVLCpiyBpgnALJ3W0aieE2UMA5HpAUZc9UQcSYbevwRcbsjeSjLoEQJcfG0D0W00" />
    <img src="http://www.plantuml.com/plantuml/png/SoWkIImgAStDuIhEpimhI2nAp5L8paaiBdOiAIdAJ2ejIVLCpiyBpgnALJ3W0aieE2UMA5HpAUZc9UQcMYa40vNbfNCfQEUcvfThbELdfcXQAO0ehbekXzIy5A3H0000" />
</p>

