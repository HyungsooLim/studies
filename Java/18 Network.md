# 18. Network

### 1. Network

- IP address : 32bit → 각 컴퓨터의 고유 주소
    - 통신을 하려면 상대방의 ip address 알아야 함
    - DNS : Domain Name System
             : 도메인 이름을 IP 주소로 바꿔줌
               ex)naver.com
    - IP주소로는 Server의 컴퓨터까지만 갈 수 있음
    - 사설 IP :
        
        <aside>
        💡 [192.168.xxx.xxx](http://192.168.xxx.xxx) → 사설 IP
        
        </aside>
        
    - 공인 IP : 공식적인 주소
- Port Number : 어떤 service를 사용하는지 알려주는 지표
    
    <aside>
    💡 192.168.xxx.xxx*:port number* 컴퓨터까지 접속 → *서비스 접속*
    
    </aside>
    
    - well known ports : 전세계적으로 지정되어 있는 포트번호
    - 0 ~ 65535번 까지의 포트번호
    - 같은 번호의 포트는 X
- TCP : 신뢰성 있는 연결
    - Client:요청 → Server:응답 O 반복
    - 중간에 끊기면 응답 → 다시 요청    ex) youtube
- UDP : 비신뢰성 연결
    - Client:요청 → Server:응답 X
    - 응답없이 일방적                            ex)dmb
- Server : Service를 제공하는 자, 컴퓨터, 소프트웨어(프로그램)
- Client : Service를 이용하는 자, 컴퓨터, 소프트웨어

<aside>
💡 IP:PN = Socket

</aside>

![18%20Network%202ad83bd490e54224aaf5bf36a22a8eba/Untitled.png](Java/18%20Network/Untitled.png)

![18%20Network%202ad83bd490e54224aaf5bf36a22a8eba/Untitled%201.png](Java/18%20Network/Untitled%201.png)

- 방화벽 허용(window)
    - 제어판 → 시스템 및 보안 → Windows Defender 방화벽 → 고급설정 → 인바운드 규칙 → 새 규칙 → 포트 → 포트번호 → 이름입력 → 종료
- Client, Server → q || Q 입력하면 서로 종료
- Thread
    - 프로그램 : 실행 가능한 파일(HDD에 저장)
    - 프로세스 : 실행 중인 프로그램(RAM에 저장)
                    Resource + Thread = Process
    - 가상의 stack을 생성해서 method 적재해서 사용
    - 동시 실행이 아니라 번갈아 가면서 실행
    1. Thread Class 상속 - 상속은 1개밖에 안되서 잘 안씀
        1. run method 오버라이딩, run이 종료되면 Thread 종료
        2. `start()` 호출 : OS에게 실행 위임
        - `sleep()` :
    2. Runnable interface 구현 - 구현은 여러개 되서 많이 씀
        1. run method 오버라이딩
        2. `start()` method 없음
        3. Thread 객체 생성시 Constructor의 인자값으로 전송
        4. Thread의 `start()` 호출
        
        ![https://postfiles.pstatic.net/MjAxOTA4MDJfOTAg/MDAxNTY0NzQwMzU0MTI3.CEB0BGL4koxw5YN-mqSSHpBmP0a8Q8Yp7YD7BpCHfZ0g.2uRZe7ijNzmQm-e8cRChoZLh-5mCgd65z0oGb-jf8CEg.PNG.lkas78/image.png?type=w773](https://postfiles.pstatic.net/MjAxOTA4MDJfOTAg/MDAxNTY0NzQwMzU0MTI3.CEB0BGL4koxw5YN-mqSSHpBmP0a8Q8Yp7YD7BpCHfZ0g.2uRZe7ijNzmQm-e8cRChoZLh-5mCgd65z0oGb-jf8CEg.PNG.lkas78/image.png?type=w773)
        
    3. 주의점
        - Dead Lock