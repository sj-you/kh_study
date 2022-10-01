# MyBatis

*SQL 문장의 수행을 대신 처리한다.*

1. Mapper XML 파일에 조장
2. 자바 인터페이스의 추상메소드에 저장 (어노테이션 안에 추상메소드를 붙여서)


### 준비하기
    
다운로드 (Maven 중앙 저장소에서 → pom.xml)

```xml
<dependency>
    <groupId>org.mybatis</groupId>
    <artifactId>mybatis</artifactId>
    <version>3.5.10</version>
</dependency>
```

MyBatis 설정파일 생성

1. 설정파일의 이름 : 자유이지만 통상 mybatis-config-xml 이라고 지정
2. 설정파일을 생성하고 , XML 파일의 위치는  src/main/resources 에 저장
    

### 동적 SQL 작성하기

*Mapper.xml 파일*

```xml
<select 
    id="FindBoardsBytitle" 
    resultType="org.zerock.myapp.domain.BoardVO">

        SELECT * 
        FROM TBL_BOARD

        <where>
            <if test="search != null">
                title LIKE '%'||#{title}||'%'
            </if>
        </where>
</select>
```

prefixOverrides="AND | OR" → AND나 OR 가 필요없을시 삭제

```xml
<select id="findBoardsByBnoAndTitle" resultType="org.zerock.myapp.domain.BoardVO">
    SELECT * 
    FROM TBL_BOARD

    <trim prefix="WHERE" prefixOverrides="AND | OR">
        <if test="bno != null">
            bno > #{bno}
        </if>

        <if test="title != null">
            AND title LIKE '%'||#{title}||'%'
        </if>

    </trim>
</select>
```

@TestInstance(Lifecycle.PER_CLASS)

```java
// JUnit jupiter  test Framwork이, 개발자가 만든 테스트 클래스의 테스트 메소드를 수정할때,
// 텟트 인스턴스(객체)를 어떤 단위로 생성할 것인가를 지정하는 어노테이션
// 1. PER_CLASS : 테스트 메소드가 몇개가 있단 하나의 인스턴스를 가지는 모튼 테스트를 수행
// 2. PER_METHOD : 테스트 메소드 마다 인스턴스를 생성해서, 해당 테스트 메소드를 수
@TestInstance(Lifecycle.PER_CLASS)
public class AppTest {

} // end class
```

이 테스트 클래스에 만든 테스트 메소드의 실행순서를 정하는 기준을 설정하는 메소드				 1. @see MethodOrderer.MethodName				: 메소드 이름을 정래서 실행순서 결정
2. @see MethodOrderer.DisplayName			: 테스트 메소드 표시이름을 정렬
3. @see MethodOrderer.OrderAnnotation 		: Order 어노테이션으로 테스트 메소드 실행순서 결
4. @see MethodOrderer.Random					: 무작위로 순서를 매번 지정

### 자동 SQL 문장 처리방식

```xml
자동SQL 문장 처리방식
======================================================================= //
자동SQL문장실행방식으로 쿼리수행 : 단 이 방식은 몇가지 규칙을 지켜야 함:
======================================================================= //
(1) 이 메소드가 수행할 SQL 문장을 Mapper XML 파일에 등록.
(2) 위 (1) Mapper XML 파일의 위치는, 이 Mapper Interface의 패키지 구조 아래에 만들어야 함.
(3) 위 (1) Mapper XML 파일의 이름은, 반드시 이 Mapper Interface의 이름과 동일하게 만들라!
(4) 위 (3) 에서 만든 Mapper XML 파일의 `namespace` 속성의 값은, 반드시 
		이 Mapper Interface의 FQCN으로 지정하라!!
(5) 자동실행시킬 SQL 문장을 가지고 있는 태그의 `id` 속성의 값은, 반드시 
		아래의 추상메소드의 이름과 동일하게 지정하라!!!
```

### Mapper XML 작성법

```xml
<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE mapper
    PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
    "http://mybatis.org/dtd/mybatis-3-mapper.dtd">

<mapper namespace="org.zerock.myapp.mapper.TimeMapper"> // 인터페이스 경로

    <select
    	id="getCurrentTime2"
    	resultType="java.lang.String">
        SELECT to_char(current_date, 'yyyy/MM/dd HH24:mi:ss') AS now FROM dual
    </select>

</mapper>
```
