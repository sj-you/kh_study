- 열거타입
    
    > 열거타입으로 지정하면 지정한 것 말고는 들어갈수 없다.
    > 
    > 
    > 열거타입의 변수 선언은 첫글자는 대문자로 한다.
    > 
    > 사용할때 변수 앞에 선언한다. ex) Week num
    > 
    > 같은 열거타입인 경우에도 다르면 저장하지 못한다.
    > 
    > 열거타입은 참조타입 이기 떄문에 null을 입력할수 있다.
    > 
    
    ```java
    // 이름을 정할때 한번애 볼수있게 한다.
    	public enum Week { MONDAY, TUESDAY, WEDNESDAY, THURSDAY,
     DRIDAY, SATURDAY, SUNDAY } // 열거상수
    
    	
    	public static void main(String[] args) {
    		
    		Week day = Week.MONDAY;
    		System.out.println(day);
    ```
    
