# Lambda

- 람다식 이란?
    
    *자바 8부터 함수적 프로그래밍을 위해 람다식을 지원한다.*
    
    *람다 계산식에서 사용된 식을 프로그래밍에 대입한 것 이다.*
    
    *자바는 람다식을 함수적 인터페이스의 익면 구현 객체로 취급한다,*
    
- Functional Interface
    - 오로지 단 1개의 추상메소드를 가진 인터페이스를 의미한다.
    - 인터페이스의 구성멤버
        1. 추상메소드
        2. 상수 (static final 상수)
        3. default method
        4. static method
  
  
*람다식의 구현대상이 되는, 함수적 인터페이스를 해당 람다식의 “**Targat Type**”라고 한다.*

```java
Runnable task = () -> { // 람다식을 이용한 익명구현객체 생성
			System.out.println("Anonymous::run() invoked"); 
		};
```

실행결과 : lambda.TTT$$Lambda$1/0x0000000800c00a00@3a71f4dd

- 람다식 작성법

```java
public static void main(String[] args) {
		MyFunctionalInterface fi;   // 타겟 파일
		
		// void method  --> (1) 매개변수선언부 그대로 가져오기 (2) 중괄호 블록 생성
		fi= () -> { // 다형성1
			String str = "method call1";
			
			System.out.println(str);
		};	// 람다식을 이용한, 함수적 인터페이스에 대한 "익명구현객체" 생성
		
		fi.method();	// 인터페이스 추상메소드 호출 -> 다형성 2

	}
```

- 람다식 구조  
    _자바 컴파일러에 의해 익명의 구현클래스가 만들어지고 인터페이스의 추상 메소드를 오버라이딩한다._
