# 생략조건

- 람다식 생략조건 1  
_람다식의 실행블록 안의 실행문장이 단 하나라면, 중괄호기호 마저도 생략이 가능하다._

```java
// 람다식의 실행블록의 실행문장을 1개로 줄임
fi = () -> System.out.println("method call3");

fi.method();
```

- 람다식 생략조건 2  
_매개변수가 오직 1개뿐이면 타입과 ( )도 생략이 가능하다._

```java
    fi= x -> System.out.println(x * 5);

    fi.method2(2);
```

- 람다식 생략조건 3  
_중괄호블록 안의 실행문장이 만일, return 문장이면, return도 생략 가능하다_

```java
// fi = (x, y) -> { return x + y; };
fi = (x, y) -> x + y;
System.out.println(fi.method(2, 5));
```

*생략을 하기 전 코드를 보자 체감이 확 온다.*

```java
    fi = (int x, int y) -> {
      int result = x + y;
      return result;
    };
```
