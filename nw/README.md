
# NW

- 클라이언트 : 서비스 요청자
- 서버 : 서비스 요청을 수신,  처리 하고 응답을 생성, 반환 한다.
- 웹
    1. 클라이언트(웹브라우저) - 서버(웹서버) 모델의 대표적인 케이스 ⇒  [cs modal]
    2. Torrent (클라이언트-서버 역할을 동시에 실행) ⇒ p2p modal
- netcat : 서버 역할을 하는 프로그램을 쉽게 만들어주는 툴   
```
    💡 nc -L -p 7777 
```
- telnet : 원격접속화면 프로그램
```
    💡 telnet <IP주소> <port>
```
    
- 사이트 ip 알아보기 : nslookup 주소
- IP 주소
    - PC의 주소이다.
- Port(항구) 번호
    - XXX 호수의 의미
- DNS
    - 도메인명을 ip 주소로 변환 해주는 서비스이다. (반대도 가능 ip ⇒ 도메인)
- 네트워크 방식
    1. 유선방식
    2. 무선방식
- 지정된 IP주소와 Port 번호까지 두갸를 동시에 확인하는 방법
    - telnet < IP주소> <Post번호>
        - 한번 연결된 후 나가는법 : 컨트롤 + ]
- 인터넷
    - 전 세계의 수많은 PC 및 장비들이 우/무선 네트워크로 연결되어 있는 큰 네크워크
- WWW(World-Wide Web)
    - 인터넷을 기반으로 그 위에서 제공되는 수많은 서비스중 하나.
    - 정보의 제공(Web 1.0) 과 상호작용(정보의 제공 - Web 2.0) 을 목적으로 하는 서비스.