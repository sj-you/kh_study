### 접근제한자
 - 접근제한 강도 (아래로 갈수록 강하다)
 ```text
 1. public : 모두 접근 가능
 2. protected : 자식클래스가 아닌 다른 패키지에 소속된 클래스 접근 불가능.
 3. default : 다른 패키지에 소속된 클래스는 접근 불가능
 4. private : 모든 외부 클래스는 접근 불가능
 ```
 
 - default 는 따로 표시하지 않는다. (기본이기 때문에 지정 안할시 자동 설정)
 
 - Clazz 객체의 레퍼런스를 얻는 방법 
    
    (1) 타입명.class 속성이용:
    ```java
    Class clazz = String.class;
    ```
    (2) 참조타입명.getClass() 메소드 이용:
    ```java
    String name="Sangjun";
    
    Class clazz = name.getClass();
    ```
    
    (3) Class.forName(FQCN) 메소드 이용:
    ```java
    Class clazz = Class.forName("java.lang.String");
    ```
