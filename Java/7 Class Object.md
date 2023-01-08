# 7. Class / Object

- Java는 OOP(Object Oriented Programming, 객체 지향 프로그래밍)

- Object : 눈에 보이는 사물 또는 개념
    
     ex) 설계도로 만든 제품, 건물, 실제 회원
    
- Class    : Object를 정의한 것
    
     ex) 설계도, 시방서, 회원가입양식
    
    - Class는 서로 다른 데이터타입의 집합
    - Class 자체가 데이터타입이 됨
    - Class 내에 선언되는 변수들은 데이터타입에 제한 없음.
        - primitive type
        - reference type
            
            ex) Member member;
            
            Member [] members;
            
            int [] ars;
            
    - 멤버변수나, 멤버메소드를 사용하려면 객체부터 생성
    - Class는 멤버변수로만 이루어진 클래스도 있고
        
                     멤버메소드로만 이루어진 클래스도 있고
        
               멤버변수와 멤버메소드로 이루어진 것도 있다.
        
- Instance : Object의 개념과 거의 같음, 특정 클래스를 언급하면     instace

![7%20Class%20Object%200acf47fa93d14d379e09adb4132320dd/Untitled.png](Java/7%20Class%20Object/Untitled.png)

```java
//객체 생성 공식
클래스명 (참조)변수명 = new 클래스명();
//class에 선언된 변수와 메소드
멤버변수, 멤버메소드
instance변수, instance메소드
//객체의 멤버 사용 공식
(참조)변수명.멤버변수명
(참조)변수명.멤버메소드명()
```

```java
//변수 선언 공식
//데이터타입 변수명 = 
//객체 생성 공식
//클래스명 변수명 = new 클래스명();
//Member는 데이터타입
Member member1 = new Member(); // 회원 1명 생성된거임 <- 객체
Member member2 = new Member();

//member1, member2 -> instance
		
Scanner sc = new Scanner(System.in);
```

![7%20Class%20Object%200acf47fa93d14d379e09adb4132320dd/Untitled%201.png](Java/7%20Class%20Object/Untitled%201.png)