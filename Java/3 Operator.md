# 3. Operator

## 연산자

- 연산한 결과물을 다른 메모리에 저장해줘야함
- Java에서 연산은 같은 데이터 끼리만 가능함

```java
int num1=0;
int num2=0;
num1+num2;    -> 계산 결과를 저장하지 않아서 작동 안됨
int num3=num1+num2; -> O
```

### 1. 산술연산자

1. +
    
    a) 산술연산자 : 숫자 계산
    
    b) 연결연산자 : String을 더할 때 결과물은 String
    
2. -
3. *
4. /   :  몫 구하기
5. %  :  나머지 구하기

```java
System.out.println("Hello \"World!!\"");
```

```java
System.out.println(1+"1");   -> 11
System.out.println(1+1+"1"); -> 21
System.out.println(1+"1"+1); -> 111
System.out.println("1"+1+1); -> 111
```

### 2. 비교연산자(관계연산자)  → 이항연산자

- 같은 primitive type 끼리만 가능 → 결과물은 boolean
1. A > B         초과
2. A < B         미만
3. A >= B         이상
4. A <= B         이하
5. A == B         이퀄  → reference type 끼리는 하지 말것
6. A != B         not 이퀄    → 프로그래밍에서 !는 부정의 의미

### 3. 논리연산

- boolean 타입 연산 - 결과값은 boolean
1. boolean && boolean : and 연산
    - true && true && false - 연산순서 : 앞에서부터 순차적
    - false && true && true  - 앞에 이미 false여서 뒤 연산X
2. boolean || boolean    : or 연산
    - true || true || false - 무조건 true여서 한번에 연산 끝
    - false || true || true - 한번 더 연산해야함
3. !boolean                     : not 연산
4. 삼항연산자
    
    조건식은 결과물이 boolean
    
    조건식?조건식이 true일때 실행:조건식이 false일때 실행
    
5. 증감연산자  → 단항연산자
    - 자기 자신을 1 증가시키거나 1 감소시키는 연산자
    - 단독으로 쓸 때 선행, 후행 결과물 같음
    - 다른 항이 있거나 연산을 할 때는 달라짐
    - 후행연산은 우선순위가 제일 끝
    - 대입연산자보다 우선순위가 낮음
    1. ++A(선행)       : 1 증가      A=A+1;
        
        A++(후행)       : 1 증가
        
    2.  --A (선행)       :  1 감소     A=A-1;
        
          A--(후행)       :  1 감소
        
6. 향상된 대입연산자 → 안써도 상관없음
    
    a = a+5  →  a+=5
    
    a + a-3   →  a-=3
    
    a = a%6  →  a%=6
    
    a = b+6  →  X
    
7. 쉬프트 연산자(비트)
    1. A<<B : 정수A의 bit를 좌측으로 밀고 빈칸은 0으로 채움
    2. A>>B : 정수A의 bit를 B만큼 우측으로 밀고
        
                   A가 양의 숫자면 빈칸을 0으로 채우고
        
             A가 음의 숫자면 빈칸을 1로 채움
        
    3. A>>>B : 정수A의 bit를 B만큼 우측으로 밀고 빈칸은 전부 0으로 채움
    
    ![3%20Operator%20b40b2932cb5d47fb8ae4bb0bff2343a7/Untitled.png](Java/3%20Operator/Untitled.png)
    
    ![3%20Operator%20b40b2932cb5d47fb8ae4bb0bff2343a7/Untitled%201.png](Java/3%20Operator/Untitled%201.png)
    
    ![3%20Operator%20b40b2932cb5d47fb8ae4bb0bff2343a7/Untitled%202.png](Java/3%20Operator/Untitled%202.png)
    
8. 비트논리연산자
    - 0 : False        1 : True
    1. A&B : and 연산
    2. A|B : or 연산
    3. ~A : not 연산
        
        ![3%20Operator%20b40b2932cb5d47fb8ae4bb0bff2343a7/Untitled%203.png](Java/3%20Operator/Untitled%203.png)
        
        ![3%20Operator%20b40b2932cb5d47fb8ae4bb0bff2343a7/Untitled%204.png](Untitled%204.png)