# 2. Variable / 형변환

### 변수 / 형변환

### 1. 변수 (Variable)

1. 변수(variable) : 변하는 수
    -   하나의 값을 저장하는 *메모리* 상의 공간
2. 상수: 변하지 않는 수
3. 리터럴(literal) : 변수에 넣는 상수 데이터
4. 데이터 타입(자료형)과 변수
    - 데이터 타입의 선택은 리터럴의 타입을 보고 결정
    
    A. Primitive Type(원시타입, 기본타입) : 더 이상 쪼갤 수 없는 데이터
    
        ex) *숫자 - 1) 정수형 : 소수점이 없는 숫자
    
    - byte - 1byte    -128~127      → bit를 다워랴 할 때
    - short - 2byte   -32768~32767 → C 언어와 호환
    - int - 4byte       -20억~20억
    - long - 8byte    -???~??? → int와 구별하기 위해 리터럴 뒤에 L붙임
    
    ```java
    int num = 5000000000; -> X
    long num = 5000000000; -> X
    long num = 5000000000L; -> O
    ```
    
                   2) 실수형 : 소수점이 있는 숫자
    
    - float - 4byte     : double과 구별하기 위해 리터럴 뒤에 F
    - double - 8byte  → 소수점 길이가 더 김
    
        *문자 - 한 글자만 담는 타입 → 리터럴 앞뒤로 ' ' 작성
    
                   char    : 2byte
    
        *논리 - 참(true), 거짓(false)
    
                   boolean  : 1byte
    
    B. Reference Type(참조타입) : 여러가지 데이터타입으로 구성된 타입
    
    - 문자열 = String : 문자열 담는 타입
    
    ```java
    String name="___";
    String name=null;
    ```
    

---

### 2. 형변환 - 형태의 변환

- Primitive Type 끼리만 가능
- 단, boolean Type은 제외
- 수의 표현 갯수가 더 많은 것이 기준(long>int>short>byte)
- 작은것에서 큰것으로 변환 → 자동형변환
- 큰것에서 작은것으로 변환 → 강제형변환
- 형식
    
    A=(형변환 할 데이터타입)B
    

```java
int num=0;
long num2=0;
num2=(long)num;
```

1. 자동형변화(묵시적 형변환) - 작은것에서 큰것으로 변환
    - 형변환 할 데이터타입 표시를 삭제(생략) 가능
    - 데이터의 변환이 없음
2. 강제형변환 - 큰것에서 작은것으로 변환
    - 형변환 할 데이터타입은 무조건 표시
    - 데이터의 변환이 있을 수 있음

*컴퓨터는 소수점 표현을 정확하게 할 수 없음 → 근사치를 제공

ex) 1 = 1.00000000000001

         = 1.00000000000002

- 실수가 정수보다 더 많은 데이터 개수를 가지고 있음

```java
long num1 = 20L;   //long = 8byte
float num2 = 3.2F; //float = 4byte
// num1 = num2; -> float가 long으로 자동형변환 예상
	num1 = (long)num2;  // 강제형변환
// num2 = num1; -> long이 float로 강제형변환 예상
	num2 = num1;		// 자동형변환
```

```java
int point = 290;
double avr = point/3;
//결과값 소수점으로 바꾸기
	double avr = (double)point/3;
	double avr = point/(double)3;
	double avr = point/3.0;
```

```java
//총점을 담을 변수
int total = 290;
		
//평균을 담을 변수
double avr = 0.0;
		
//과목 수는 3과목		
//최종결과물 소수점 2자리 까지만 출력
avr = total/3.0; // 값 = 96.6666666666
		
avr = avr*100;        // 9666.666666
int result = (int)avr; // 9666
avr = result/100.0;    // 96.66
```

---

- 메모리 단위
    
    1GB = 1024MB
    
    1MB = 1024KB
    
    1KB = 1024BYTE
    
    1BYTE = 8BIT
    

엔지니어 : 최소단위 bit

개발자     : 최소단위 byte

![128+64+32+16+8+4+2+1 = 255](sieve-bitmask.png)

128+64+32+16+8+4+2+1 = 255

1byte로 표현 할 수 있는 최대 수 255

- Java에서의 1byte

![2%20Variable%20%E1%84%92%E1%85%A7%E1%86%BC%E1%84%87%E1%85%A7%E1%86%AB%E1%84%92%E1%85%AA%E1%86%AB%20ad72b871ce0940c09d350ff3437955b9/Untitled.png](Java/2%20Variable%20형변환/Untitled.png)

![2%20Variable%20%E1%84%92%E1%85%A7%E1%86%BC%E1%84%87%E1%85%A7%E1%86%AB%E1%84%92%E1%85%AA%E1%86%AB%20ad72b871ce0940c09d350ff3437955b9/Untitled%201.png](Java/2%20Variable%20형변환/Untitled%201.png)