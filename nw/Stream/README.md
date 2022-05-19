
# 스트림

     스트림은 정보의 흐름 이라고 생각하면 된다.
- 바이트 기반 스트림
    - 그림, 멀티미디어, 문자 등 **모든 종류의 데이터를 받고 보낼수 있다.**
- 문자 기반 스트림
    - 오로지 **문자 타입의 데이터**를 주고 받을수 있다.

### 문자기반 
---

- **입력** (Reader 문자기반)
     - 입력 스트림으로부터 1 바이트를 읽고 읽은 바이트를 리턴한다.     
     - read(byte[] b)의 형태로 배열에 저장하고 리턴할수 있다.
     - read(byte[] b, int off, int len) : len개의 바이트 만큼 읽고 주어진 배열을 b부터 lne 까지 저장후 len개를 리턴한다
- **출력** (Writer 문자기반)
     - 출력 스트림으로 매개값으로 주어진 한 문자를 보낸다.
     - 입력과 같이 배열에 담아 보낼수 있다. ex) write(char[] cbuf)
     - 입력과 같이 offset과 len을 지정하여 보낼수 있다. (문자열 포함)
     - write(String str) : 출력 스트림에 매개값을 문자열로 전부 보낸다.    
     - 출력스트림 사용시 잔류하는 문자열이 있을 수 있으니 _.flush()를 꼭 수행한다._
### 입출력 메소드
---
- 입출력 메소드  

  모든 입출력 메소드는 기본적으로 blocking I/O 이다. (입력 받아야 넘어감)
    
    ```java
    InputStream is = System.in;
    		
    		byte[] datas = new byte[100]; 
    		
    		System.out.print("이름 : ");
    		int nameByte = is.read(datas);
    		String name = new String(datas, 0, nameByte-2);
    		
    		System.out.print("하고 싶은말 : ");
    		int commentBytes = is.read(datas);
    		String comment = new String(datas, 0, commentBytes-2); 
    		// -2 ==> 엔터키는 제외하는 용도
    ```
    
### 파일 입출력
---
_파일 시스템의 파일을 표현하는 클래스(File class)이다.  
파일의 크기,속성,이름 등의 정보를 알려주며 생성, 파일 리스트를 가져올수 있다._ 

**FileOutputStream**  
파일이 이미 존재할 경우, 데이터를 출력하게 되면 파일을 덮어쓰는 단점이 있다.  
기존 파일 내용 끝에 데이터를 추가할 경우
```java
FileOutputStream fis = new FileOutputStream("경로", true);
FileOutputStream fis = new FileOutputStream(file, true);
```
    
     
    
    
    
