# 8. method

- 메소드 선언 방법

```java
접근지정자 그외지정자 리턴타입 메소드명(매개변수선언) {}
접근지정자   : 모르면 무조건 public
그외지정자   : 모르면 생략
리턴타입    : 모르면 무조건 void
매개변수선언 : 모르면 생략
```

- 메인메소드 내의 내용처럼 작성
    - if, for, while, 객체생성, 변수 선언 등 전부 사용 가능
- 매개변수와 인자값
    - 메소드 내부에 필요한 데이터를 받기 위해 선언
    - 매개변수의 선언하는 갯수의 제한이 없음(' , ' 구분)
    - 데이터타입 제한X
    - 매개변수의 메소드 내에 선언하는 지역변수
    - 인자값 : 메소드로 보내는 값(매개변수에 대입하는 값)
- 리턴타입
    - 호출된 메소드가 종료시 호출한 곳으로 돌려줄 데이터가 있을때 사용
    - return하는 데이터의 데이터타입
    - 타입선언은 한개만 가능
    - 데이터도 한개만 가능
    - void : return 할 것이 없음
    - 메소드 내에서 return을 만나면 그 즉시 메소드는 종료
    - 메소드가 실행하는 영역은 '}' 끝을 만나거나 return을 만날 때 까지 실행
- 메소드 호출
    
    ```java
    참조변수명.멤버메소드();
    ```
    
    ![8%20method%20eb04d743d7c64e68af7820df20e25c62/Untitled.png](Java/8%20method/Untitled.png)
    
    ![8%20method%20eb04d743d7c64e68af7820df20e25c62/Untitled%201.png](Java/8%20method/Untitled%201.png)
    
    ---
    
    1. 프로그램은 위에서 밑으로 내려가면서 실행
    2. 변수는 메모리에 생성
    3. 메모리에 있는 변수를 사용하려면 메모리의 주소를 알아야 사용
    4. stack에 선언되는 변수
        - Primitive Type이면 변수에 실제데이터가 저장
        - Reference Type이면 변수에 실제데이터를 가리키는 메모리의 주소가 저장
    
    ```java
    public String memberLogin(Member[] members) {
    		Scanner sc = new Scanner(System.in);
    		System.out.println("ID 입력");
    		int id = sc.nextInt();
    		System.out.println("PW 입력");
    		int pw = sc.nextInt();
    		String name=null;
    		for (int i = 0; i < members.length; i++) {
    			if (id == members[i].id && pw == members[i].pw) {
    				name = member[i].name;
    				break;
    			}
    		}
    		return name;
    	}
    ```
    
    ```java
    public int memberLogin(Member[] members) {
    		Scanner sc = new Scanner(System.in);
    		System.out.println("ID 입력");
    		int id = sc.nextInt();
    		System.out.println("PW 입력");
    		int pw = sc.nextInt();
    		int idx = -1;
    		for (int i = 0; i < members.length; i++) {
    			if (id == members[i].id && pw == members[i].pw) {
    				idx = i;
    				break;
    			}
    		}
    		return idx;
    	}
    ```
    
    ```java
    public Member memberLogin(Member[] members) {
    		Scanner sc = new Scanner(System.in);
    		Member member = new Member();
    		System.out.println("ID 입력");
    		int id = sc.nextInt();
    		System.out.println("PW 입력");
    		int pw = sc.nextInt();
    		Member result = null;
    		for (int i = 0; i < members.length; i++) {
    			if (id == members[i].id && pw == members[i].pw) {
    				result = members[i];
    				break;
    			}
    		}
    		return result;
    	}
    ```