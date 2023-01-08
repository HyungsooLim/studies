# Java 기초

## 1. 객체 지향 프로그래밍 (OOP)

### 1. 함수 호출과 스택 메모리

- 스택 : 함수가 호출될 때 지역 변수들이 사용하는 메모리
- 함수의 수행이 끝나면 자동으로 반환 되는 메모리

![Untitled](Java/Fastcampus%20-%20All%20In%20One/Java%20기초%203ddb52857cdd427abf4ff92b905b1f0f/Untitled.png)

```java
public class FunctionTest {
	
	public static int addNum(int num1, int num2) {
		int result;
		result = num1 + num2;
		return result;
	}
```

### 2. 인스턴스 생성과 힙 메모리

- 인스턴스 (instance)
    - 클래스는 객체의 속성을 정의하고, 기능을 구현하여 만들어 놓은 코드 상태 → Ready 상태
    - 실제 클래스를 기반으로 실제 사용할 객체 → instance
    
    ```java
    Student Lim = new Student();
    ```
    
- 동적 메모리 (Heap Memory)
    - 생성된 인스턴스는 heap에 할당됨
    - Java에서 Garbage Collector가 주기적으로 사요하지 않는 메모리를 수거
    - 하나의 클래스로부터 여러개의 인스턴스가 생성되고 각각 다른 메모리 주소를 가지게 됨
    
    ![Untitled](Java/Fastcampus%20-%20All%20In%20One/Java%20기초%203ddb52857cdd427abf4ff92b905b1f0f/Untitled%201.png)
    
- 용어 정리

```
    객체 : 객체 지향 프로그램의 대상, 생성된 인스턴스

    클래스 : 객체를 프로그래밍 하기위해 코드로 정의해 놓은 상태

    인스턴스 : new 키워드를 사용하여 클래스를 메모리에 생성한 상태

    멤버 변수 : 클래스의 속성, 특성

    메서드 : 멤버 변수를 이용하여 클래스의 기능을 구현한 함수

    참조 변수 : 메모리에 생성된 인스턴스를 가리키는 변수

    참조 값 : 생성된 인스턴스의 메모리 주소 값
```

### 3. static과 메모리

- 인스턴스가 생성될 때 만들어지는 변수가 아닌, 처음 프로그램이 메모리에 로딩될 때 메모리를 할당
- 클래스 변수, 정적 변수
- 인스턴스 생성과 별개이므로 클래스 이름으로 직접 참조

![Untitled](Java/Fastcampus%20-%20All%20In%20One/Java%20기초%203ddb52857cdd427abf4ff92b905b1f0f/Untitled%202.png)

![- 프로그램을 메모리에 할당할 때 Data, Code 영역이 생김
- Data 영역 = 상수, Literal, static 등…
- Code 영역 =  작성한 코드들이 들어감](Java%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%203ddb52857cdd427abf4ff92b905b1f0f/Untitled%203.png)

- 프로그램을 메모리에 할당할 때 Data, Code 영역이 생김
- Data 영역 = 상수, Literal, static 등…
- Code 영역 =  작성한 코드들이 들어감

### 4. static 응용 - 싱글톤 패턴 (singleton pattern)

- 싱글톤 패턴이란?
    - 프로그램에서 인스턴스가 단 한개만 생성되어야 하는 디자인 패턴
    - static 변수, 메서드를 활용하여 구현할 수 있음
    - ex) Calendar 클래스 … 등
    
    ```java
    public class Company {
    
    	//
    	private static Company instance = new Company();
    
    	//
    	private Company() {
    
    	}
    
    	//
    	public static Company getInstance() {
    		if(instance == null) {
    			instance = new Company();
    		}
    		return instance;
    	}
    
    }
    ```
    
    ```java
    Company company1 = Company.getInstance();
    Company company2 = Company.getInstance();
    
    // 두 변수의 메모리 할당 위치가 같게 나옴. -> 같은 Company 클래스
    ```
    

## 2. String, StringBuilder, StringBuffer, text block

### 1. String 클래스

- String 선언
    
    ```java
    // Heap 영역에 생성
    String str1 = new String("abc");
    // 상수pool에 생성
    String str2 = "abc";
    ```
    
- 한번 생성된 String은 불변(immutable)
- String을 연결하면 기존의 String에 연결되는 것이 아닌 새로운 문자열이 생성됨
    - 기존 문자열이 남아서 메모리 낭비 발생

### 2. StringBuilder, StringBuffer 활용

- 내부적으로 가변적인 `char[]` 를 멤버 변수로 가짐 → String은 `final` 변수에 저장됨
- 문자열을 여러번 연결하거나 변경할 때 유용
- 새로운 인스턴스를 생성하지 않고 `char[]` 를 변경함
- StringBuffer는 멀티 쓰레드 프로그래밍에서 동기화(synchronization)을 보장
- 단일 쓰레드 프로그램에서는 StringBuilder 사용 권장
- toString() 메서드로 String 반환

### 3. text block 사용

- 문자열을 `“”” “””` 사이에 이어서 만들 수 있음
- html, json 문자열을 만드는데 유용

```java
public class StringTextBlock {

	public static void main(String[] args) {
		
		String strBlock = """
				This 
				is 
				text
				block
				test.""";
		System.out.println(strBlock);
		
		System.out.println(getBlockOfHtml());
		
	}
	
	public static String getBlockOfHtml() {
		    return """
		            <html>
		                <body>
		                    <span>example text</span>
		                </body>
		            </html>""";
		
	}

}
```