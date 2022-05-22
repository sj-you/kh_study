# 보조스트림  

_다른 스트림과 연결되어 여러가지 편리한 기능을 제공해주는 스트림이다._  

보조스트림 생성하는법
```java
보조스트림 변수 = new 보조스트림(연결스트림)
```

- 성능향상 보조스트림  
_입출력 소스와 직접 연결하지 않고 버퍼와 작업하면 성능이 향상된다. ( 프로그램 -> 버퍼 -> HDD)_  
  
- 객체 입출력 보조 스트림
객체를 파일 또는 네트워크로 입출력할 수 있는 기능을 제공한다.  

  
- 객체 직렬화 (Serializable)  
_객체는 문자가 아니므로 바이트 기반 스트림으로 데이터 변경이 필요하다.  
 이럴 때 꼭 필요한 것이 **Serializable**이다. 우리가 만든 클래스가 파일에 읽거나 쓸 수 있도록 하거나,  
 다른 서버로 보내거나 받을 수 있도록 하려면 반드시 이 인터페이스를 구현해야 한다._
  ```java
 	// *** 직렬화 제외하고 싶은 필드 앞에 transient
	transient int field4; 	// transient => 일시적인
  ```
  
  직렬화를 진행할시 serialVersionUID을 지정할수 있으며 지정 하는것을 권장한다.
  ```java
  private static final long serialVersionUID = 1L; // Serializable 사용시 반드시 필요
  ```
  ```
  💡 직렬화를 진행할때 정해진serialVersionUID 와 복구할 serialVersionUID 가 다르면 복구를 할수 없다.

  - serialVersionUID 을 지정하지 않을시 JVM이
    
  컴파일을 수행할때마다 변경된다.
  ```
1. **부모/자식 모두Serializable 한 경우**  
	_자식객체를 직렬화 할 때 ===> 자식만이 아니라, 부모객체까지 함께 직렬화된다(기본 직렬화 동작)_
     
2. **부모만 Serializable 하고, 자식은 Non-serializable**  
    _자식 객체를 직렬화 하면 ===> 위 1번과 같다. (***)_    
    _즉, 부모의 Serializable 한 성질이 자식에게도 상속된다. (*******)_
    
3. **부모만 Non-Serializable 하고, 자식은 Serializable 할 때**  

     _자식 객체를 직렬화 하면 ===> 자식객체만 직렬화 된다. (위 1,2와 다른 결과)_ 
  
4. **부모만 Non-Serializable 하고, 부모소스는 다른 벤더에서 만큰 클래스가 소스의 수정불가 / 자식은 Serializable 할 때**   
 
	_자식 클래스에 아래의 2개의 메소드를 추가하고, 이 메소드 안에서,
	직렬화/역직렬화가 애시당초 불가능한 필드에 대해서는, InputStream/OutputStream이 제공하는
	메소드로 직접 입/출력을 수행하고, 나머지 Serializable 한 필드는 JVM이 하듯이 동일하게 처리._  
	```java
	private void writeObject(ObjectOutputStream out) throws IOException { ... }
	private void readObject(ObjectInputStream in) throws IOException, ClassNotFoundException { ... }
	```
  
