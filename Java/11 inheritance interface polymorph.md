# 11. inheritance / interface / polymorph

## 상속(Inherit, 확장,extends)

### 상속

- 부모로부터 상속, 자식이 사용
- 부모클래스(Super Class)의 멤버들을 자식클래스(Child Class)에서 사용
- 클래스들 간의 공통요소(멤버)가 있다면 공통요소를 부모클래스로 작성 후 자식클래스가 상속 받아 사용.
    1. 공통요소를 재활용
    2. Class 간의 관계를 설정
        - 수직으로만 관계 O
        - 수평으로는 관계 X
    3. 생성자는 제외
- super, super()
    - super : 부모객체의 주소를 담고 있는 참조변수
    - super() : 부모의 생성자를 호출
                  생성자에 첫줄 위치
                  생략가능
- 상속의 조건
    - 상속 : 자식클래스명 is a 부모클래스명 → 상속
    - 포함 : 자식클래스명 has a 부모클래스명 → 멤버로
- 추상클래스
    - 완성되지 않은..
    - 단독으로 객체 생성 X
    - 상속(확장)해서 사용
    - 일반클래스처럼 멤버변수, 멤버메소드, 생성자 가짐
    - 추상메소드를 가질 수 O
    - 클래스내에 한개 이상의 추상메소드가 있다면 해당 클래스는 추상 클래스로 선언
    
    ```java
    접근지정자 abstract class 클래스명
    ```
    
- 추상 메소드
    - 메소드의 선언부(head)만 있는 메소드
    - 상속해서 오버라이딩 해서 사용
    
    ```java
    접근지정자 abstract 리턴타입([매개변수선언]);
    ```
    

```java
public class Parent {			
					public void info() {
					}
}

public class Child extends Parent {

								public void info(){} //오버라이딩
																		 //내용이 같아도 다시 선언하면 오버라이딩 O

								public void info(int num) {} // 오버로딩

								public void ch1() {} // 메소드 선언

								public void ch1(int i) {} // 오버로딩
								
								public void ch1() {} // 에러
```

### Interface와 구현(implements)

- 추상 클래스와 비슷
- 추상 클래스보다 추상화가 더 심한것
- 클래스와 같은 개념  → 클래스로 보면 됨
- 상수, 추상메소드를 멤버로 가짐
- 표준화
- 관계가 없는 클래스 간에 관계를 맺어줄 때 사용
- 인터페이스도 다형성 관계가 성립
- 다른 인터페이스 상속 가능
- 인터페이스가 인터페이스를 상속할 때는 extends 씀
    
    ```java
    interface명 extends interface2명
    ```
    

```java
public interface FlyAble {

	//상수 -> 잘 안씀
	final int num=3;
	//추상메소드
	//접근지정자는 public
	//그외지정자 abstract
	public abstract void fly();
	
	//run
	void run(); //public abstract 자동생성
	
	public void start(); //abstract 자동생성
}
```

- Java는 단일 상속만 가능
- 인터페이스는 다중 구현이 가능
- 상속 하나에 인터페이스 여러개 구현 가능

```java
public class 클래스명 extends 상속할 클래스명 implements 인터페이스명,인터페이스명...
```

### 다형성(Polymorph)

- 상속관계에서만 가능
- 부모타입의 변수는 부모가 알고 있는 영역까지만 접근 가능
- 형변환과 비슷한 개념
    - int → double
    - double → int
- 변수에는 선언된 데이터타입과 같은 타입만 대입 가능
- 클래스는 사용자가 만든 데이터타입
- 자식클래스명 is a 부모클래스명
- 자식데이터타입 == 부모데이터타입