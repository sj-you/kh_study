- 메소드
    - void
        ```
        💡 메소드가 호출자에게 되돌려줄 값이 없도록 설계되었다면 void을 사용한다.
        
        ```
        
    - return
        
        ```
        💡 정의된 타입으로 값을 반환한다.
        ```
        
    - 객체와 객체간에 상호작용 수단 =⇒ 객체의 “메소드 호출” 이다.
    - 메도스의 매개변수 : 필요한 데이터를 외부에서 받기 위해 사용

- Lombok 을 이용하여 기본생성자 사용하기
    
    ```java
    import lombok.NoArgsConstructor;
    
    @NoArgsConstructor
    ```
    
- 변수에 배열을 담지 않고 매개변수를 넘겨주는 방법 [new 연산자를 사용한다]
    
    ```java
    int result1 = myCom.sum1(new int[] {1,2,3,4,5});
    ```
    
- return
    
    > 
    > 
    > 
    >  return 키워드를 만나는 즉시, 메소드의 실행 종료
    >  return 키워드 다음에 값이 나오면, 이 값을 호출자에게 반환
    > 
    > (1) literal
    > 
    > (2) 변수
    > (3) 표현식 ==> 연산식
    > (4) 리턴타입에 일피하는 값을 반환하는 다른 메소드 호출
    > 
- 가변인자
    - 가변인자 사용시 가변인자를 뒤쪽에 배치해야 한다.
    - 다른 타입의 매개변수라도 예외는 없다.
    
    ```java
    int sum2(int i, int ...values) {}
     // ... ==> 가변인자 (0개 이상)  가변인자 == 배열
    ```
    

 

- Object 는 모든 클래스의 조상이다.
- Getter 메소드
    
    <aside>
    💡 Getter : 필드의 값을 반환해주는 메소드 =⇒ ‘’get” + 필드명() {}
    
    </aside>
    
- Setter 메소드
    
    <aside>
    💡 Setter : 필드의 값을 변경해주는 메소드 ‘set’ + 필드명() {}
    
    </aside>
    
- 다음은 자바빈즈(JavaBeans) 클래스 규약이다.
    1. private 접근제한자로 필드를 선언한다.	        (필수)
    2. getter 메소드와 setter 메소드를 갖는다.	(필수)
    3. 기본 생성자가 반드시 존재해야 된다.	        (필수)
    4. implements Serializable	                                (선택)
