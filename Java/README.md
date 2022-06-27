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
   * 0~11월로 표현했어야 했는데 1~12로 표현 가능

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

***
