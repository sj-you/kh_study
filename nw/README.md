
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
 
 - WAN : 지역 네트워크를 통신 회선으로 연결한것 이다.
- **LoopbackAddress**
    - 자기 자신의 주소를 의미한다.
- 여러개의 주소 가져오기.
    - 가져온 주소 값이 음수일 경우 256을 더해줘야 한다.
    
    ```java
    // 주어진 도메인명이 dNS에 등록된 모든 IP주소를 가져와서 주소를 구성하는 각 정수 출력하는 예제
    		InetAddress addr = InetAddress.getByName("naver.com");
    		byte[] addBytes = addr.getAddress();
    		log.info("\t+ b: {}", Arrays.toString(addBytes));
    		
    		for(byte b : addBytes) {
    			log.info("\t+ b: {}", (b < 0)? b+256 : b);
    		} // enhanced for
    ```
    
- URL : Uniform Resource Locator
    - (단일화된 방법으로 웹상의 자원의 위치를 알려주는자)
- URI : Uniform Resource Indicator
    - (단일화된 방법으로 웹상의 자원을 가리키는 지시자)

- https -- 통신규약(웹에서는 2개로 정해져 있음: http / https ) 
- http: HyperText Transfer Protocol Secure
 
- :<Port>  -- 서버프로그램의 포트번호를 작성
    
> 네트워크 특징
> 
> 
> TCP/IP Networking
> 
> TCP : 전송제어 통신규약 <-> UDP (User-Datagram Packet): 편지봉투
> 
> IP   : Internet Protocol (인터넷 통신규약)
> IP주소와 Port 번호로 연결생성
> 
- socket 은 양방향인데 수신작업이 모두 종료되면, 수신만 먼저 닫을 수 있다.
    
    ```java
    sock.shutdownInput();
    ```
- accept : 동작을 완료할수 있을때 까지 중지하는 용도
- 자원객체를 사용하면 다 사용한후 꼭 close();을 사용하여 닫아야 한다
- try
    
    ```java
    try(serverSocket){	// () 안에 반드시 close 해야할 자원객체의 참조변수를 넣는다
    			;;	    // 이 {} 안에서, 무언가 수행하다 반드시, 예외가 발생하든 안하든
    					// {} 안에서 serverSocket 에 저장된 자원객체를 사용하는곳
    		}	// try with-resources
    ```
    

- 타입 변환.

```java
byte bValue = Byte.parseByte("10");		// 기본타입으로 반환
Byte byteObj = Byte.valueOf("10");		// 참조타입으로 반환
```
