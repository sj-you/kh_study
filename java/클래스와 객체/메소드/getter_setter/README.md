- Getter 메소드
    - 각 필드의 값을 반환해주는 메소드(기능)
    - 매개변수를 가지지 않음(필드의 값을 반환하는 기능이기 때문에)
    - 메소드의 이름을 지을 때, 아래와 같은 규칙으로 한다(***)
    
    ``` java
     'get'(prefix) + <필드명> => 필드타입 get필드명()   { ... }
    
     예: private String name = "Sangjun";
    
        'get' + name ==>
    
        // name 필드에 대한 Getter 메소드 선언
        public String getName() {
           return this.name;
        } // getName
    
    ```
- Setter 메소드
    - 각 필드에 새로운 값을 대입(변경)해주는 메소드(기능)-
    - 매개변수를 가져야함(필드에 넣어줄 새로운 값이 필요)
    - 메소드의 이름을 지을 때, 아래와 같은 규칙으로 만든다.(***)
    
    ```java
     'set'(prefix) + <필드명> => void set필드명(필드타입 매개변수명) { ... }
    
     예: private String name = "Sangjun";
    
        'set' + name ==>
    
        // name 필드에 대한 Setter 메소드 선언
        public void setName(String name) {
           this.name = name;
        } // getName
    
    ```
