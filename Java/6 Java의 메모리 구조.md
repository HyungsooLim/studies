# 6. Java의 메모리 구조

## 변수

- 메모리에 데이터를 저장
- 데이터를 찾아가려면 메모리의 주소를 알고 있어야함
- 메모리의 주소는 16진수로 구성

### 1. 변수 구분 기준

- 데이터 기준
1. Primitive Type
    - byte, short, int, long, float, double, char, boolean
    - 변수에 실제 데이터가 저장
2. Reference Type
    - Primitive Type 제외한 나머지
    - String, Scanner, Array, ...
    - 변수에 실제 데이터가 있는 메모리의 주소가 저장

### 2. 메모리 기준

1. 지역변수
    - Stack 영역에 선언된 변수
    - 메소드{} 내에 선언
    - if, for 등 {}내에 선언
    - { 시작되면 생성되고, }만나면 삭제
2. 멤버변수, instance 변수
    - Heap 영역에 선언된 변수
    - new 연산자 실행시 생성
    - 참조변수를 잃어버리면 삭제가능
3. 클래스변수
    - Static 영역에 선언된 변수
- Java는 프로그램 실행 시 3개의 메모리 구조를 가진다.
    - 메소드영역(Static 영역)
    - Stack 영역
    - Heap 영역
        - Heap 영역에 만들어진 변수들은 자동 초기화됨.

![6%20Java%E1%84%8B%E1%85%B4%20%E1%84%86%E1%85%A6%E1%84%86%E1%85%A9%E1%84%85%E1%85%B5%20%E1%84%80%E1%85%AE%E1%84%8C%E1%85%A9%207b728425e21948b89dbdb2e1bf619a17/Untitled.png](Java/6%20Java의%20메모리%20구조/Untitled.png)

***모든 변수는 초기화 해야 사용 가능***

- 지역변수는 개발자가 초기화를 수동으로 진행
- Heap에 만들어지는 데이터들은 자동으로 초기화 진행

![6%20Java%E1%84%8B%E1%85%B4%20%E1%84%86%E1%85%A6%E1%84%86%E1%85%A9%E1%84%85%E1%85%B5%20%E1%84%80%E1%85%AE%E1%84%8C%E1%85%A9%207b728425e21948b89dbdb2e1bf619a17/Untitled%201.png](Java/6%20Java의%20메모리%20구조/Untitled%201.png)

- primitive type에 선언된 변수 제외 모두 참조변수
    - = Reference type에 선언된 변수는 참조변수
    
    참조변수 = 주소