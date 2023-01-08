# 17. java.io

### 1. java.io(Input, Output)

- 기준 : 현재 프로그램 기준
- Stream : 양방향 통신 시 2개의 Stream 필요
    1. 입력 Stream
    2. 출력 Stream
1. InputStream
    - Byte 단위 처리
    1. int read() : 입력 스트림으로부터 다음 Byte를 읽음
    2. int read(byte[] b) : 입력 스트림으로부터 다음 Byte를 읽어서 바이트 배열에 저장
        - 공통사항 : 더 이상 읽을 byte가 없으면 -1 리턴
2. OutputStream
    - Byte 단위 처리
    1. write(int b) : 출력 스트림으로 해당 바이트를 출력
    2. write(byte[] b) : 출력 스트림으로 해당 바이트 배열만큼 출력
3. Reader
    - 문자 단위 처리
4. Writer
    - 문자 단위 처리
    
    * 문자 기반 보조스트림
    
    1. BufferedReader
    2. BufferedWriter

### 2. java.io.File

- HDD의 파일 또는 폴더의 정보를 다루는 클래스

```java
File file = new File("부모 폴더의 경로명", "자식폴더명이나 파일명");
file file = new File("폴더나 파일의 경로명");
```

1. exists() : 지정한 파일이나 폴더가 존재하면 true, 아니면 false
2. isFile() : 파일이면 true, 아니면 false
3. isDirectory() : 디렉토리 true, 아니면 false
4. mkdir() : 디렉토리 생성, 부모 디렉토리가 없다면 생성 실패
5. mkdirs() : 부모 디렉토리가 없다면 부모 포함해서 자식 디렉토리 생성
6. createNewFile : 파일을 생성
7. delete() : 파일 또는 디렉토리 삭제, 디렉토리는 내부가 비어있어야 삭제 가능
8. list() : 해당 경로의 디렉토리 내에 파일과 디렉토리 이름을 String[] 로 리턴
9. listFiles() : 해당 경로의 디렉토리 내에 파일과 디렉토리 이름을 File[] 로 리턴
10. getName() : 파일이나 디렉토리의 이름을 리턴
11. length() : 파일이나 폴더의 크기 반환

### 3. java.io.FileWriter

- 파일에 내용을 작성

```java
생성자(파일의 경로명)
생성자(파일의 경로명, boolean)
								- true : 동일한 파일명이 있는 경우 기존 내용 뒤에 쓰기
								- false : 동일한 파일명이 있는 경우 기존 파일 제거하고 새로 작성(덮어쓰기)
```

1. write("작성한 메세지")
2. flush() : buffer를 강제로 비우기
3. close() : 데이터? 닫기
    - flush, close 는 필수로 쓰기

### 4. java.io.FileReader

- 문자 기반
- 문자열을 읽을려면 보조스트림 BufferedReader가 필요

![17%20java%20io%201769ec062b54410ca099fa13dcb6d7d2/Untitled.png](Java/17%20java%20io/Untitled.png)

### 5. java.util.UUID

- `UUID.randomUUID().toString();` : 중복되지 않는 이름 생성