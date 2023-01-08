# 16. Date / Time

### 1. java.util.Calendar

- 날짜와 시간을 다룰 때 사용

```java
Calendar cal = Calendar.getInstance();
```

1. get(int field) : 각 변수에 맞는 날짜와 시간 등을 반환
2. getTimeInMillis : 현재 시간을 milli second로 반환
3. set(int field, int value) : 각 변수에 해당하는 값으로 변환
4. setTimeInMillis(long mill) : milli second로 시간 변환
5. getTime() : Calendar 객체를 Date라는 객체로 반환
6. roll(int field, int amount) : 해당 field에 amount 만큼 흐르게함
                                             →  다른 필드에는 영향 X
7. add(int field, int amount) : 해당 field에 amount 만큼 흐르게함
                                             →  다른 필드에는 영향 O
8. after(Object calendar) : 현재 Calendar가 매개변수로 받은 객체의 시간보다 나중이면 true
9. before(Object calendar) : 현재 Calendar가 매개변수로 받은 객체의 시간보다 이전이면 true
    
    <aside>
    💡 Month(월) 은 +1 -1 주의
    
    </aside>
    

### 2. java.text.SimpleDateFormat

1. format(Date) : Date를 패턴에 맞는 문자열로 반환
2. applyPattern("패턴") : 패턴 변경
3. toPattern() : 현재 패턴을 문자열로 반환