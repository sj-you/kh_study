# DDL  

*다양한  DB객체를 생성/삭제/변경하는 문장이다.*

```sql
CREATE    - DB객체(= Oracle 객체) 생성
ALTER     - DB객체(= Oracle 객체) 변경
DROP      - DB객체(= Oracle 객체) 삭제
RENAME    - DB객체(= Oracle 객체) 이름 변경
TRUNCATE  - DB객체(= Oracle 객체) 정보 절삭
```

테이블(Table) - 데이터 저장  
*기본적인 데이터 저장 단위로, 행과 열로 구성된 객체*

인덱스(Index) - 데이터 검색성능 향상  
*테이블에 저장된 데이터의 검색 성능 향상 목적을 위한 객체*

뷰(View) - 가상의 테이블  
*한 개 이상의 테이블의 논리적인 부분 집합을 표시할 수 있는 객체*

시퀀스(Sequence) - 순차번호 생성기  
*테이블의 특정 컬럼값에 숫자 값 자동 생성 목적을 위한 객체*

동의어(Synonym) - 테이블의 별칭  
*객체에 대한 동의어를 설정하기 위한 객체*  
  
  
- ON DELETE SET NULL
    
    *참조하는 부모 테이블의 행이 삭제되면, 해당 행을 참조하는 자식 테이블의 컬럼값을 NULL로 설정한다.*
    
    ```sql
    CREATE TABLE emp02(
        empno   NUMBER(4)
            CONSTRAINT emp02_empno_pk PRIMARY KEY,
        ename   VARCHAR2(15),
        deptno  NUMBER(2)
            CONSTRAINT emp02_deptno_fk
                REFERENCES dept02(deptno) s -- 삭제시 참조값 NULL
    );
    ```
    

- Flashback Drop

```
💡 나. 테이블 삭제할 때, (DROP TABLE tablename;)
삭제된 테이블은 휴지통(RECYCLEBIN)이라는 특별한 객체에,
 'BIN$' prefix가 붙은, 이름으로 저장됨.
```

```
💡 3. 삭제된 테이블을 다시 복구하고 싶을 때, Flashback Drop
복구기술을 이용하여, 휴지통(RECYCKEBIN) 객체에서, 삭제된
테이블을 복구할 수 있다.
```

데이터 사전(Data Dictionary Viwe)  

1.  DBA_XXXX : 데이터베이스 관리자만 접근가능한 객체 등의 정보조회
2.  ALL_XXXX : 자신계정 소유 또는 권한을 부여받은 객체 등에 관한 정보조회
3.  USER_XXXX: 자신의 계정이 소유한 객체 등에 관한 정보조회
