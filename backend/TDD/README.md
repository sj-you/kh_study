# TDD (Test-Deiven Development)

*테스트- 주도 개발*


## JUnit ver 4x

  숙지 어노테이션

  1. @Before : 테스트(@Test) 수행전, 사전준비작업이 필요할때

  ![image](https://user-images.githubusercontent.com/88135939/187611017-ffa9a40b-b80b-4efd-8826-24b07a3166a3.png)


  반드시 기본생성자가 필요하다. (@NoArgsConstructor)

```java
  @Before
  public void setup() {
    log.trace("setup() invoked.");
    // 주로 테스트 메소드 수행에 필요한 각종 자원객체를 얻거나 환경설정
  }

  @Test
  public void testXXX1() { // 이름은 반드시 testXXX로 한다 (버전4)
    // 테스트의 목적대로 테스크 코드의 수행결과가 사전에 기대했던 값과
    // 일치하는지 여부를 검정흐는 코드가 매소드 블록 마지막에 주로 나옴 
    log.trace("testXXX1() invoked.");
    String result = null;
    assertNotNull(result);

    log.info("\t+ OK");
  }

  @After
  public void tearDown() {
    log.trace("tearDown() invoked.");
    }
```

---    
    
### JUnit ver 5x

테스트 클래스로부터, 테스트 객체를 생성하는 방법이 2가지이다 (@TestInstance)

1. PER_CLASS -> 1개만 생성
2. PER_METHOD -> 테스트 메소드 수행마다

테스트 메소드의 순서를 정할수 있다. (@TestMethodOrder)

구성

@BeforeAll

@BeforeEach

@Test → 속성지정가능

```java
@Test
@Order(2) // 실행순서
@DisplayName("contentLoad1") // 이름
@Timeout(value=1, unit = TimeUnit.SECONDS) // 타임아웃
void contentLoad1() {
  log.trace("contentLoad1() invoked");
}
```

@AfterEach

@AfterAll

Clazz 가져오기

1. 타입명.class
2. 참조변수명.getClass()
3. Class.forName(문자열타입의 FQCN)

