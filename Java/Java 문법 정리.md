# Java 문법 정리

2021년 2월 10일 

```java
접근지정자 [그외지정자] class 클래스명 extends 부모클래스명 implements 인터페이스명...{
	//생성자
	접근지정자 클래스명([매개변수선언]) {
	}

	//멤버변수
	접근지정자 [그외지정자] 데이터타입 변수명;

	//멤버메소드
	접근지정자 [그외지정자] 리턴타입 메소드명([매개변수선언]) {

			//지역변수 선언
			데이터타입 변수명;

			//객체생성
			클래스명 참조변수명 = new 생성자호출();

			//instance 멤버 사용
			참조변수명.멤버변수명;
			[리턴타입 변수명] = 참조변수명.멤버메소드명([인자값]);

			//class 멤버 사용
			클래스명.변수명;
			[리턴타입 변수명] = 클래스명.메소드명([인자값]);

			//if, switch, for, while, do-while, break, continue
			//배열
	}
}
```

- Java 메모리 영역
    1. Static - 클래스변수
    2. Stack - 지역변수
    3. Heap - 인스턴스변수
- Java 메모리 타입
    1. Primitive
    2. Reference