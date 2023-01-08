# 13. java.lang. ~

### Library (API)

- 클래스 내에서 사용하는 다른 클래스는 현재(같은) 패키지 내에서 찾음.
- import에 사용하려 하는 클래스의 풀패키지명을 명시
- java.lang에 있는 클래스들은 기본 제공되므로 import를 사용하지 않고 사용 가능.

```java
// java.util.패키지 내의 모든 클래스를 사용하겠다
import java.util.*;

웬만하면 쓰지 말자
```

- 문서에선 접근지정자 안써있으면 = public

### java.lang.Object

- 모든 클래스의 조상(부모, 타입)
- 모든 클래스는 Object 타입
- 주요 method
    1. equals : 두개의 참조변수가 같은지 비교
    2. toString : 객체의 주소를 반환
                  : 참조변수 출력하면 자동으로 toString이 호출

### java.lang.String

- 문자열
- 문자열 변형, 일부분의 데이터 추출 등
- 주요 method
    1. charAt : 문자열에서 해당 인덱스번호의 문자를 반환
    2. equals : 문자열의 값이 서로 같은지 비교(Overriding)
    3. indexOf : 제공하는 문자의 인덱스 번호 리턴,
                    없으면 -1 리턴  * 앞→뒤
    4. lastIndexOf : 제공하는 문자의 인덱스 번호 리턴,
                         없으면 -1 리턴  * 뒤→앞
    5. length : 문자열의 크기 리턴
    6. isEmpty : 문자열의 크기가 0이면 true, 아니면 false 반환
    7. replace : 문자(열)을 변환하고 반환
    8. toCharArray : 문자열을 문자배열로 반환
    9. toLowerCase : 문자열을 전부 소문자로 바꿔서 반환
    10. toUpperCase : 문자열을 전부 대문자로 바꿔서 반환
    11. trim : 문자열의 앞뒤 공백을 제거하고 반환. 중간의 공백
              은 제거X → replace
    12. valueOf : 다른 데이터타입을 문자열로 변환 후 반환
    13. subString : 문자열에서 원하는 부분만 추출
        - beginIndex - 시작인덱스부터 끝까지
        - beginIndex, endIndex - beginIndex~endIndex미만
    14. split : 어떤 기준으로 문자열을 분리
        
        ** parsing : 데이터를 쪼갠다.**
        
    
    regex = regular expression ( 정규표현식 )
    

### java.lang.StringBuffer

- String은 불변
- 문자열+문자열은 새로운 문자열을 생성하기 때문에 메모리 낭비
- StringBuilder와 동일(Thread에 안전한것은 Buffer)→ Buffer 쓴다.
- 주로 여러개의 데이터를 연결해서 하나의 문자열로 생성.
1. append()

### Wrapper

- 감싼다.
- Primitive Type을 Reference Type으로 변경(감싼다)
    - char    →   Character
    - byte    →   Byte
    - short   →   Short
    - int       →   Integer
    - long    →   Long
    - float    →   Float
    - double →  Double
    - boolean → Boolean
    
    ```java
    		int num = 10;		
    		Integer n1 = new Integer(num);
    		num = n1; //auto unboxing
    		n1 = num; //auto boxing
    		
    		double d = 3.14;
    		n1 = (int)d;  //같은 datatype끼리만 가능
    ```
    
1. 클래스명.parse클래스명() : 문자열을 primitive type으로 변경

### java.lang.Math

- 수학에 관련된 method
- 클래스변수, 클래스메소드로 이루어짐
1. ceil :  올림
2. floor : 내림
3. round : 반올림
4. random : 0.0~1.0 사이의 랜덤한 실수