- **배열**

---

```
💡 같은 타입의 데이터를 연속된 공간에 저장하는 자료구조. [element]
```

```
💡 자바의 배열은 한번 생성하면 크기와 원소의 타입을 봐꿀 수가 없다.
```

1.  값을 알고 있을시 { } 을 사용하여 생성한다.
2.  향상된 for문 !! (다만 꺼내는 위치는 지정할수 없다)

```java
for(int element : array) {
			System.out.println(element);
		} // enhanced for ( 향상된 for)
```

1. 보기 좋게 배열 출력하는법

```java
		// 3rd. method
		System.out.println(Arrays.toString(scores));
```

- **new 연산자 : 객체생성연산자**

-**배열을 선언하고 아무값도 입력하지 않으면 해당 타입의 기본값이 들어간다.**
