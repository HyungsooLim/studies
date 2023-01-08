# 4. if- & For-

## Statement

 * Scope : 영역  {   }

- 영역 내에서 선언된 변수는 해당영역이 종료되면 같이 사라짐

- 클래스 영역을 제외한 { } 내에 선언된 변수를 지역 변수라 함

- Life Cycle(생명주기)

### 1. 조건문 If

1. 단일 if 
    
    ```java
    if(조건식) {
    		조건식이 true일때 실행
    }
    ```
    
2. 둘중에 하나를 실행하는 if - else
    
    ```java
    if(조건식) {
    		조건식이 true일때 실행
    }else {
    		조건식이 false일때 실행
    }
    ```
    
3. 여러가지 중에 하나 선택 if -else if -else if -else  : 다중if
    
    ```java
    if(조건식1) {
    		조건식1이 true일때 실행
    }else if(조건식2) {
    		조건식2가 true일때 실행
    }else if(조건식3) {
    		조건식3이 true일때 실행
    }else {
    		조건식1,2,3이 모두 false일때 실행
    }
    ```
    
4. switch - case : 여러개 중 하나를 선택
    - 정수식 : 결과물이 정수
    - 일치하는 case를 실행하고 break를 만나거나, switch의 끝부분을 만날때까지 실행
    - 범위를 나타낼때 좋지 않다. ↔ if else가 더 편하다.
    - 정수형 == 판별은 switch case가 좋다.
    
    ```java
    switch(정수식 or 문자열) {
    		case 상수1 or 문자열:
    		break;
    		case 상수2 or 문자열:
    		break;
    		case 상수3:
    		...
    		default:
    		break;
    }
    ```
    

### 2. 반복문

1. For
    - 몇번 돌릴지 알때 씀 ↔ while문
    
    ```java
    for(초기식;조건식;증감식) {
    			조건식이 true일때 실행
    }
    ```
    
    - 작동순서
        1. 초기식 - 무언가를 초기화한다.
        2. 조건식
            - 조건식이 true면
                1. { } 실행
                2. 증감식
                3. 조건식         -     반복
            - 조건식이 false면 for문 종료
    
    * 이중 for문
    
    ```java
    for(초기식;조건식;증감식) {
    
    		for(초기식2;조건식2;증감식2) {
    		
    		}
    }
    ```
    
    - 향상된 for문
        - 인덱스 번호가 필요 없을 때
        
        ```java
        for(모은데이터타입 변수명:모은 변수명){
        
        }
        
        //ex)
        int[] ar = new int[3];
        
        for(int num : ar){
        	System.out.println(num);
        }
        ```
        
2. While
    - 얼마만큼 돌려야할지 모를때 사용↔for문
    
    ```java
    while(조건식) {
    		조건식이 true일때 실행
    }
    ```
    
    ```java
    do{
    
    }while(조건식);
    ```
    
3. 보조문
    - continue
        
        - for 문 내에서 continue를 만나면 그 즉시 증감식으로 이동
        
        - while문 내에서 continue를 만나면 그 즉시 조건식으로 이동
        
    - break
        
        - 반복문 (for, while) 에서 break를 만나면 그 즉시 반복문 종료
        
        * 이중 반복문 내에서 보조문을 만날 경우 해당 반복문만 적용
        
        ```java
        for( ) {
        	~~~~~~~
        	continue;
        }
        ----------------------
        for( ) {
        	~~~~~~~
        	break;
        }
        ```
        
        ```java
        boolean check = true;
        
        		while (check) {
        			System.out.println("1. 회원가입");
        			System.out.println("2. 로그인");
        			System.out.println("3. 종료");
        			int select = sc.nextInt();
        
        			switch (select) {
        			case 1:
        				System.out.println("회원가입 코드 진행");
        				break;
        			case 2:
        				System.out.println("로그인 코드 진행");
        				break;
        			default:
        				System.out.println("프로그램 종료");
        				check=false;
        				break; // <-이거 쓰면 끝나지 않음
        			}
        		}
        ```