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
