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

### Index (인덱스)

*데이터베이스 성능에서 매우 중요한 역할을 담당하며 단순컬럼, 복합컬럼에 대해*   
*인덱스 생성이 가능하다.*  

```sql
 가. 인덱스 객체 안에는 크게 아래의 두가지 정보를 가지고 있음:
     (1) ROWID - 테이블의 각 행의 논리적인 주소값 저장
     (2) 단순/복합 컬럼 - 인덱스를 생성한 컬럼 데이터
 나. 실제 데이터(각 행)의 논리적 주소인 ROWID를 사용하면,
     Table Full Scan 방식이 아닌, Index Scan 방식을 사용하여,
     검색된 데이터를 테이블에서 랜덤하게 블록에서 접근가능.
 다. ROWID(각 행의 논리적 주소값)를 저장하고 있는 오라클 객체가 인덱스임
 라. 인덱스 안의 ROWID 정보를 이용하여, 필요한 데이터를 검색하는 방식
     이를, Index Scan 이라 한다.
 마. 인덱스는 ROWID + Column Datas 를, B-tree 구조로 저장
     (B-tree.jpg 이미지 참고)
```

Index 구조

- HashTable
    
    *해시 테이블은 key와 value를 한 쌍으로 데이터를 저장하는 자료구조이다.  
    (key, value)로 쌍을 표현하며, key값을 이용해 대응되는 value값을 구하는 방식이다.*
    
- B+Tree
    
    *B+Tree는 오직 leaf node에만 데이터를 저장하고 leaf node가 아닌 node에서는 자식 포인터만 저장하며,   
    leaf node끼리는 Linked List로 연결되어 있다.*  
    

Index 생성

*PK / UK 제약조건 생성시, Unique Index 가 자동으로 생성된다.*

```sql
-- Basic syntax:
CREATE [UNIQUE] INDEX 인덱스명
ON 테이블(컬럼1[, 컬럼2, ...]);
--
(1) Unique Index
	  a. CREATE UNIQUE INDEX 문으로 생성한 인덱스
		b. Index 내의 Key Columns에 중복값 허용하지 않음
		c. 성능이 가장 좋은 인덱스
		d. (*주의*) 중복값이 허용되는 테이블 컬럼에는 절대로 사용불가!!
(2) Non-unique Index
		a. CREATE INDEX 문으로 생성한 인덱스
		b. 중복값이 허용되는 테이블 컬럼에 대해,
			 일반적으로 생성하는 인덱스
```

Index 적용시점

1. *테이블에 데이터가 많거나 특정 컬럼값의 범위가 작은 경우.*
2. *WHERE (빈도수가 높은) 절이나 Join 조건에 사용되는 컬럼.*
3. *DQL 쿼리결과의 크기가, 전체 데이터의 2 ~ 4 % 이내를 검색하는 경우.*
4. *NULL 값을 많이 포함하는 컬럼의 경우.*
