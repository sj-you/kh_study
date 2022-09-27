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
