# Spring

### 설정
```
(1) log4j2.xml
    이 로그 설정파일에서 핵심은, 개발자가 로그를 보고 싶은 라이브러리의 "패키지"를 지정해서
    새로운 Logger를 등록하는 것
   
   예: <Logger name="org.springframework" level="info" />
                   스프링 프레임워크에서 남기는 info 레벨의 로그를 보자!!!

(2) web.xml     =======> **** (Servlet, listener)
     가. Spring Container 를 생성하는 Listener 가 자동등록 (설정파일: root-context.xml 사용됨)
     나. Front Controller(모든요청을 집중해서 받는) 패턴으로 구현된 DispatcherServlet 등록되어있음(설정파일: servlet-context.xml)

(3) pom.xml     =======> **** (주로 dependency)

     핵심: 스프링 등을 비롯한 반드시 필요한 라이브러리에 대한 의존성 설정(dependency)
            (스프링 기반으로 웹어플리케이션 생성시 반드시 필요한 2가지 라이브러리는,
            1)  `spring-context` (Spring Container 생성에 필요)
   2) `spring-webmvc` (Spring MVC 패턴을 강제하는데 필요)`
            스프링의 필수 라이브러리

(5) 스프링MVC의 설정파일  ==> web.xml 에 이미 등록
    가. Spring Container 생성역할하는 ContextLoaderListener의 설정파일 => root-context.xml
    나. Spring MVC 를 강제하는, Front Controller역할을 수행하는 DispatcherServlet의 설정파일 =>
         servlet-context.xml

* Static Documents (정적인 문서) : 아무리 매번 요청해서 받아도, 그 내용이 변함이 없는(정적이다!표현을 쓰는
  것임) 파일들을 지칭 (예: 각 종 이미지파일, *.css, *.js, *.html, ....) => 이런 파일들은 모두 webapp/resources/*
   에서 저장 및 서비스 한다!!!
http://localhost:8080/resources/video/2.mp4
 ===> 어디서 찾느냐? /resources/video/2.mp4

* TDD - Test-Driven Development

* WAR - Web Archieve (동일한 압축파일) => XXXX.war
* JAR   - Java Archieve (동일한 압축파일) => XXXX.jar
```
