# 12. Exception

### 예외처리

- 예외(Exception)가 발생하면 프로그램이 그 즉시 강제종료
- 비정상적인 종료를 막고 정상적으로 프로그램이 실행 될 수 있도록 개발자가 처리
- 에러(error)의 일종
- 에러 : Compile error
ex) 코드에 빨간줄
- 예외 : 실행시 발생하는 error
- Object ← Throwable ← Exception ← RuntimeException ← 하위 예외 클래스
1. try - catch
    - 하나의 try 문에 여러개의 catch 구문 가능
    
    ```java
    try {
    			//예외가 발생할 것 같은 구문들
    } catch(발생한 예외 객체타입 선언) {
    			//예외 처리 구문
    } catch(발생한 예외 객체타입 선언) {
    
    } finally {
    			//예외가 발생하든 안하든 무조건 실행되는 구문
    }
    ```
    
2. Throws → 협업때 씀
    - 예외처리를 위임
    
    ```java
    메서드 선언부(매개변수 선언) throws 발생한 예외객체명 {
    
    }
    ```
    
3. 사용자 정의 예외 클래스
    - Class를 선언하고 Exception 클래스를 상속

<aside>
💡 `e.printStackTrace()` : Exception 출력해주는 method
                                         : 프린트

</aside>