# SQL
sql의 용도:  _본인이 정한 조건에 맞는 데이터를 요구하는 용도이다._


### Synonym (동의어)

*DB 객체에 대한 별칭이며 DB 객체에 대한 접근방법을 단순화 시킨다.*

*동의어를 사용시 객체접근 단순화와 보안문제를 해결할수 있다.*

```sql
(1) private
	 a. 동의어를 만든 사용자만 사용가능
	 b. 일반 계정으로 생성/삭제 가능
(2) public
   a. 모든 사용자가 사용가능
   b. DBA권한 가진 관리자만이 생성/삭제 가능
-- ex) DUAL    ->  SYS.DUAL
```

기본문법

```sql
-- Basic Syntax:
CREATE [PUBLIC] SYNONYM 동의어
FOR 스키마.객체 ;
```

### Sequence :  순차번호(Sequential number) 생성기

*호출될 때마다, 자동으로 숫자를 생성하는 Oracle 객체이며,*

*테이블의 특정 컬럼의 값을 Numbering 할 때 사용한다.*

기본문법

```sql
--  Sequence
CREATE SEQUENCE dept_deptno_seq
    START WITH 10       -- 10부터
    INCREMENT BY 10     -- 10증가
    MAXVALUE 100        -- 최대 100
    MINVALUE 5          -- 최소 5
    CYCLE               -- 최대 도달시 MINVALUE부터
    NOCACHE;            -- 최대 20개의 숫자를 메모리에 미리 생성하지 않음
```

```sql
[ START WITH n ] 
		순차번호의 시작값 지정. 생략시 1부터 시작

[ INCREMENT BY n ] 
		연속적인 순차번호의 증가치 지정. 음수도 가능 (감소치), 생략시 1씩 증가

[ MAXVALUE n | NOMAXVALUE ] 
		시퀀스 객체가 생성할 수 있는 순차번호의 최대값 지정

[ MINVALUE n | NOMINVALUE ]
		시퀀스 객체가 생성할 수 있는 순차번호의 최소값 지정
		아래 CYCLE 옵션이 지정된 경우, 새로 시작하는 값 역할

[ CYCLE | NOCYCLE ]
    시퀀스 객체가 최대값(MAXVALUE) 까지 증가한 경우,
    START WITH 값 부터 재시작 하는 것이 아니라, MINVALUE 값 부터 재시작
     
[ CACHE n | NOCACHE ]
    성능향상을 위해, 메모리 상에 미리 순차번호를
    기본으로 20개까지 미리 생성하여 관리.
    (*주의사항*) DB를 종료 했다가, 재시작하면, 이전에 미리 생성하였었던,
		메모리에 있는 최대 20개의 순차번호는 재사용불가     
    NOCACHE는 , 필요할 때 마다, 매번 순차번호 계산하여 반환
```
