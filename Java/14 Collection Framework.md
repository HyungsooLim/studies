# 14. Collection Framework

### 1. Collection Framework

- 주요 인터페이스
    1. java.util.List
        - 순서가 유지, 값의 중복 허용
        - index 번호 기반(배열기반)
        - Collection Interface 상속
    2. java.util.Set
        - 순서 유지 X, 값의 중복 허용 X
        - Collection interface 상속
    3. java.util.Map
        - 키(key)와 값(value)로 구성
        - key는 중복 허용 X, value는 중복 O
        - 순서 유지X
    4. java.util.Iterator
        - 반복자
        - Map의 Key → Set → Iterator

### 2. java.util.ArrayList    -   가장 많이 씀

- ArrayList<모을려고 하는 데이터타입> 변수명 = new ArrayList<>();
1. add(Object e) : 새로운 데이터를 끝에 추가
    
           (int idx, Object e) : 해당 인덱스번호에 데이터를 추가
    
2. get(int index) :  해당 인덱스번호의 요소를 리턴
3. size() : 요소의 갯수를 리턴
4. remove(int index) : 해당 인덱스번호의 요소를 삭제
5. clear() : 모든 요소를 삭제
6. set(int idx, Object e) : 해당 인덱스번호의 요소를 e로 수정
- java.util.LinkedList ↔  ArrayList와 비교
    - List 구현

### 3. java.util.HashSet

- Collection 인터페이스 구현
- List와 비슷한 메소드 (add...)
- iterator 이용해서 출력

### 4. java.util.HashMap

- Map 인터페이스 구현
1. put(key, value) : 해당 key로 value 추가
                           : 이미 있는 key라면 수정
2. get(key) : 해당 key로 value를 반환
3. clear() : 전체 삭제
4. remove(key) : 일치하는 key와 value를 삭제
5. remove(key, value) : key와 value도 일치해야 삭제
6. containsKey(key) : 해당 key가 Map에 있으면 true, 없으면 false
7. containsValue(value) : 해당 value가 Map에 있으면 true, 없으면 false
8. keySet() : key들을 Set Interface 타입으로 변경 후 반환

### 5. 제네릭(Generic)

- Class나 method 등에서 사용할 내부 데이터타입을 컴파일시 미리 지정하는 방법
- DataType의 안전성을 보장
- 타입의 변경(Casting)이나 타입 검사등의 노력을 줄임.

```java
<? extends T>
						- T(부모)와 부모를 상속 받는 자식 타입 전부 포함하겠다.
								
<? super T>
						- T(자식)와 T의 부모들 타입 전부 포함하겠다.
```