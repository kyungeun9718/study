# Java
네트워크상에서 쓸 수 있도록 미국의 선 마이크로 시스템즈가 개발한
`객체 지향 프로그래밍` 언어
***
## Java8 특징
* Lambda : 하나의 메소드를 식으로 표현하는 것
   * 코드의 간결성
   * 내장된 메서드 사용가능
```java
Runnable java7Runner = new Runnable(){
    public void run(){
        System.out.println("Lambda");
    }
};
Runnable java8Runner = () ->{
    System.out.println("Lambda");
};
```
* JDK 1.1 Calendar class의 문제점 해결 가능
   * 불변객체가 아니여서 값이 수정될 수 있었으나 수정 불가능.
   * 0월부터 11월로 표현되었으나 1월부터 12월로 표현 가능

* Nashorn
   * 새로운 js엔진 도입
***
## Class, Object, Instance
* Class (클래스)
   * 객체를 만들어 내기 위한 `설계도`
   * 연관되어 있는 변수와 메서드의 집합

* Object (객체)
   * 소프트웨어에 구현할 `대상`
* Instance (인스턴스)
   * 소프트웨어에 구현된 구체적인 `실체`
   * 인스턴스는 객체에 포함된다고 볼 수 있음
   * 실제로 메모리로 할당된 상태

```java
//Class
public class Fruit{
    ...
}
public class Main{
    public static void main(String[] args){
        Fruit apple, banana; //Object
        
        apple = new Fruit(); //apple은 Fruit Class의 Instance. 객체를 메모리에 할당
        banana = new Fruit();
    }
}
```
***

## 객체 지향 프로그램(OOP : Object Oriented Programming)

### OOP의 4가지 특징
1. 캡슐화
   * 실제로 구현한 부분을 외부에 나타내지 않게 하는 것
   * 클래스의 내부 변수와 메소드를 하나로 묶는 것
   * 데이터를 외부에서 접근하는 것이 아닌 함수로 접근하는 것
      * public : 같은 프로젝트 내에서 사용 가능
      * protected : 같은 패키지 내, 다른 패키지에서 상속받아 자손클래스에서 접근 가능
      * default : 같은 패키지 내에서 접근 가능
      * private : 같은 클래스 내에서 접근 가능


2. 상속
   * 자식클래스가 부모 클래스의 기능, 속성을 물려받은 것
   * 코드의 변경이 용이하며, 재사용성을 높여줌
   * 클래스 + 자식클래스 + extends + 부모클래스 적음으로써 상속클래스를 작성가능
   ```java
   class Child extends Parent{
   ...
   }
   ```

3. 다형성
   * 변수와 메소드가 상황에 따라 다른 결과를 나타내는 것
      * Overloading(오버로딩) : 같은 이름의 메소드를 여러개 정의하는 것
      * Overriding(오버라이딩) : 부모 클래스의 메소드를 자식 클래스의 용도에 맞게 재정의하여 코드의 재사용성을 높임. 즉 상속받은 클래스를 재정의하는 것

4. 추상화
   * 공통된 속성이나 기능을 묶어서 이름을 붙이는 것

### OOP의 5가지 원칙 (SOLID)
#### S ( SRP: Single Responsibility Principle ) 단일책임 원칙
  : 한 클래스는 하나의 책임만 가져야 한다.
#### O ( OCP : OPEN Closed Principle) 개방폐쇄원칙
  : 확장에는 열려있으나, 변경에는 닫혀있어야 한다.
#### L (LSP : Liskov's Substitution Prinsiple) 리스코프 치환 원칙
  : 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다.
#### I (ISP : Interface Segregation Prinsiple) 인터페이스 분리 원칙
  : 특정 클라이언트를 위한 인터페이스 여러 개가 범용 인터페이스 하나보다 낫다.
#### D (DIP: Dependency Inversion Prinsiple) 의존 역전 원칙
  : 추상화에 의존하나, 구체화에 의존하면 안된다.
***

### Overloading vs Overriding
* Overloading
  * 같은 이름의 메소드를 여러개 정의하는 것
  * 매개변수의 타입이 다르거나 개수가 달라야 한다.

* Overriding
  * 상속에서 나온 개념
  * 상속받은 상태에서 본문 내용만 수정하는 것

***

### GET & POST
* GET
  * 클라이언트에서 서버로 데이터를 전달할 때, 주소 뒤에 이름과 값이 결합된 스트링 형태로 전달
  * 주소창에 스트링 형태가 그대로 보여지기 때문에 보안성이 떨어진다.
  * 기본적으로 256byte 의 길이 제한이 있다.(브라우저마다 약간씩 다름)
  * POST방식보다 상대적으로 전송 속도가 빠르다.

* POST
  * 주소창에 전송하는 데이터의 정보가 노출되지 않아 GET방식에 비해 보안성이 높다.
  * 기본적으로 데이터양이 많아서 속도가 GET방식보다 느리다.
  * 문자열 데이터 뿐만이 아니라, 라디오 버튼, 텍스트 박스 같은 객체들의 값도 전송 가능하다.

***

### Session vs Cookie  

방문자의 상태를 지속시키기 위하여 사용한다.
* Session
   * 관리주체가 서버이다.
   * Cookie에 비해 보안성이 좋다.
   * Session을 많이 사용하게 되면 Sever의 메모리를 과도하게 사용하게 되어 Sever 에 무리가 간다.

* Cookie
  * 관리주체가 클라이언트이다.
  * Cookie는 다른 사용자에 의해서 임의로 변경이 가능하여 정보 유출 가능성이 있다. (Session 보다 보안성이 낮다.)
  * 서버측에서 별도의 만료 시간을 가지고 있다.

***

### Call by Reference vs Call by Value

* Call by Reference
   * 매개 변수의 원래 주소에 값을 저장하는 방식
   * C언어의 포인터 개념
  
* Call by Value
   * 주어진 값을 복사하여 처리하는 방식
   * JAVA