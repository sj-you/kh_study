
# 테이블 변경

```
💡 
가. 생성된 테이블의 구조를 변경
  a. 컬럼의 추가/삭제
  b. 컬럼의 타입/길이 변경
  c. 컬럼의 제약조건 추가/삭제
나. ALTER TABLE 문장 사용
다. 테이블의 구조변경은 기존 저장된 데이터에 영향을 주게 됨
```

컬럼 추가  

*기존 테이블에 새로운 컬럼을 추가하며 추가된 컬럼은, 테이블의 마지막에 추가*  

```sql
ALTER TABLE EMP04
ADD ( -- NULL 허용상태 (제약조건을 추가 가능하다)
    email VARCHAR2(10),
    address VARCHAR2(20)
);
```

제약조건 삭제  

```sql
ALTER TABLE dept03
DROP PRIMARY KEY; -- 기본키 제약 삭제
```

*부모 테이블의 PK/UK 삭제시 자식 테이블의 FK 제약조건을 삭제하려면 CASCADE 옵션을 사용하면 된다. ( 권장X )*  

제약조건의 활성 / 비활성  

*제약조건은 데이터의 무결성은 보장될수 있으나 성능이 느려진다. 이러할때 사용한다. ( 다만 데이터를 입력할때 제약조건 발동 X )*  

```sql
ALTER TABLE 테이블명 
DISABLE | ENABLE CONSTRAINT 제약조건명 [CASCADE];
--
-- DISABLE : 비활성화
-- ENABLE  : 활성
-- CASCADE : 관련된 모든 제약조건 연쇄적 비활성화
```
