# 예외처리

예외(Exception)
    
_개발자가 잘못된 조작 또는 코드를 잘못 입력한 경우를 말한다.  
예외가 발생되면 프로그램 종료된다.  
예외처리를 추가하면 실행 상태로 돌아갈수 있다._

예외의 종류  
1. Checkde 예외(Exception)  
    _예외처리 코드가 없을시 발생한다._
2. Runtime 예외(RuntimeException)  
     _예외 처리 코드를 생략하더라도 컴파일이 되는 예외이다.
     실행중에 나오는 예외를 말한다._
      
예외처리(try-catch-finally)   
  ```
  try문 안에서 예외가 발생하면 catch를 이용해 예외를 잡을수 있다.  
  finally는 예외가 있든 없든 항상 실행을 한다.  
  catch(;;) 안에는 Throwable 과 Throwable의 자식클래스 만 가능하다  
  ```  
  
MulitCatch
    
  ```java
  // 위의 예외중 어떤 예외가 발생하든 같은 예외처리를 한다.
      } catch(NullPointerException | ArrayIndexOutOfBoundsException| NumberFormatException e) {
        System.out.println(e);
      }
  ```
    
catch(Throwable e) | catch(Error e)  
_모든 에러를 잡는다 -> 다형성1에 의해 부모클래스 이기떄문에 다 잡을수 있다._  

다중 catch  
_다중 catch를 작성할때는 자식 -> 부모 순으로 작성을 해야한다_
  
예외 발생시키기
```java
thrwo new NumberFormatException();
```
