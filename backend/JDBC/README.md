# JDBC (java Database Connectivity)

### 구성요소

1. JDBC API  ⇒ 인터페이스(규격만 정의)
2. JDBC Deiver
  
### 순서

(0) java.sql.DriverManager (Class) ⇒ 연결  
(1) java.sql.Connection (interface)  
(2) java.sql.Statement  (interface) ---> Dynamic SQL (잘 사용하면 안됨!!!--> 성능을 떨어뜨림)  
(3) java.sql.PreparedStatement (interface) --> Prepared SQL  
(4) java.sql.ResultSet   (interace)  
(5) java.sql.SQLException (class) - Checked Exception  
  
자원객체를 닫는 순서가 정해져 있고, 이를 반드시 지켜야 된다.  
(4) > (2) 또는 (3) > (1)

### Target DB에 접근 필수 요소

1. jdbc URL
    
    접속방법
    
    *EZCONMENT : 접속IP주소, 접속 포트번호, 접속DB이름*
    
    *TNSNAMES : EZCONMENT 의 3가지 정보를 가지고 있는 별칭을 이용*
    
    표기법
    
    *jdbc:<vendor>:thin:@IP주소:Port번호/접속DB명*
    
    *jdbc:<vendor>:thin:@네트워크 별칭 (tnsname.ora 파일 경로 지정 필요 By 환경변수)*
    
    ```java
    // JDBC Driver 연결
    private static String jdbcUrl = "jdbc:oracle:thin:@db20220510182126_high?TNS_ADMIN=C:/opt/OralcleCloudWallet/ATP";
    private static String driverClass = "oracle.jdbc.OracleDriver";
    private static String user = "HR";
    private static String pass = "Oracle12345678";
    ```
    
    driverClass 는 지정을 해주지 않아도 된다,!
    
2. Driver Class”s FQCN
3. USER
4. Pass
