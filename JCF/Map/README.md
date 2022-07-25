
# Map

*키와 값이 쌍으로 지정되며 키는 중복이 불가하다*

![캡처](https://user-images.githubusercontent.com/88135939/180714466-bfbcc1cc-ae09-435a-a195-bd7fb677a6ce.JPG)


### HashMap

*키 객체는 hashCode()와 equals()를 재정의해 동등 객체가 될 조건을 정해야 한다.*
  
  
```java
Map<String, String> map = new HashMap<>();
```

### HashTable

*키 객체 만드는 법은 HashMap과 동일하며 스레드 동기화가 된 상태이다.*

*복수의 스레드가 동시에 접근해서 객체를 추가, 삭제 하더라도 스레드는 안전*

### Properties

*키와 값을 String 타입으로 제한한 Map 컬렉션이며 프로퍼티 파일을 읽을때 주로 사용한다.*

### 프로퍼티 파일

*옵션정보, DB연결정보, 국제화(다국어) 정보를 기록 (텍스트 파일로 활용 )*

*AP에서 주로 변경이 잦은 문자열을 저장한다 ( 유지보수 편의 )*

*키값이 = 기호로 연결되어 있는 텍스트 파일 ( 한글은 유니코드 )*

### classPath

*우리가 만든 소스에서 사용한 모든 클래스(.class)를 찾아가는 경로이다.*

*classPath에 자동으로 bin 폴더가 지정되어 있다.*

### .getResource

*호출한 클래스 패키지로 기준한 상대적인(relative) 리소스 경로로 리소스를 탐색한다*

```java
String path = PropertiesExample.class.getResource("database.properties").getPath();
```
