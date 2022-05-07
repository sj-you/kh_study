- Getter 메소드
가. 각 필드의 값을 반환해주는 메소드(기능)
나. 매개변수를 가지지 않음(필드의 값을 반환하는 기능이기 때문에)
다. 메소드의 이름을 지을 때, 아래와 같은 규칙으로 한다(***)
    
    ``` java
     'get'(prefix) + <필드명> => 필드타입 get필드명()   { ... }
    
     예: private String name = "Sangjun";
    
        'get' + name ==>
    
        // name 필드에 대한 Getter 메소드 선언
        public String getName() {
           return this.name;
        } // getName
    
    ```
