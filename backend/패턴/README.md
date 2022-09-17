# 패턴

### DAO 패턴

*모듈화한 클래스들중에서 데이터베이스 처리하는 코드만을 관리하는 클래스를 작성할
수 있는데 이 클래스 파일을 DAO 클래스라고 한다.* 

***DataBase에 접근 하기 위한 로직 & 비지니스 로직**을 분리하기 위해 사용*

*이렇게 DAO 클래스를 사용해서 개발하는 것이 보편화 되었기 때문에 DAO 패턴이라고 부른다.*

### DTO

**`*DTO(Data Transfer Object)`** 는 계층 간 데이터 교환을 하기 위해 사용하는 객체로, DTO는 로직을 가지지 않는 순수한 데이터 객체(getter & setter 만 가진 클래스)이다.*

### VO

**`*VO(Value Object)`** 값 오브젝트로써 값을 위해 쓰입니다. read-Only 특징(사용하는 도중에 변경 불가능하며 오직 읽기만 가능)을 가진다.*

*DTO와 유사하지만 DTO는 setter를 가지고 있어 값이 변할 수 있다.*

### FrontController 패턴

*사용자의 요청을 처리하기 위한 최초 진입점(intial)을 정의하고 사용하는 패턴을 의미한다.*

*모든 사용자의 요청을 집중화 시키면 요청을 분산시켜 발생되는 중복된 코드를 제거할수 있다.*

M = Model    : 비지니스 로직 수행결과 데이터  
V  = View   : Model 데이터를 이용한, 응답화면을 생성  
C  = Controller   : MVC 흐름을 제어  

```java
하나의 Servlet 이다
모든 Request Message를 받는 집중화 수행
(적용패턴: Front Controller Pattern)
이를 위해, url-pattern mapping 에 달려있다!
(1) 디렉토리 패턴 : 반드시 / 로 시작해야 함
예: * or 
(2) 확장자 패턴    : 반드시 *.확장자로 끝나야 함
예: *.do
```
