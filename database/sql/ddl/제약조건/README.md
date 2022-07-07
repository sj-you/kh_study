
# 제약조건

1. *제약조건은 테이블에 부적절한 데이터가 저장되는 것을 방지한다.*
2. *데이터가 저장되기 전에, 무결성을 검사하여, 잘못된 데이터가 저장되는 것을 방지한다.*
3. *필요 시, 제약조건의 기능을 일시적으로, 활성화/비활성화 할수 있다.*

제약조건의 종류

1. NOT NULL
    
    *해당 컬럼의 값으로 NULL을 허용하지 않는다.*
    
2. UNIQUE ( column-level ) and ( table-level )
    
    *해당 컬럼의 값은 항상 유일한 값을 갖는다.*
    
3. PRIMARY KEY ( column-level ) and ( table-level )
    
    *해당 컬럼값은 반드시 존재해야 하고 유일해야 하며 테이블에서 식별자 역할을 한다.*
    
    *단순 / 복합 컬럼으로 구성될수 있으며 UNIQUE 성질로 인해 자동으로 INDEX가 생성된다.*
    
4. FOREIGN KEY ( column-level ) and ( table-level )
    
    *해당 컬럼의 값이, 다른 테이블의 컬럼의 값을 참조해야 한다.*
    
    *참조되는 컬럼에 없는경우 값은 저장이 불가능 하다.*
    
5. CHECK ( column-level ) and ( table-level )
    
    *해당 컬럼에 가능한, 데이터 값의 범위나 사용자 조건을 지정한다.*
    

```
💡 제약조건의 이름짓기
명명방법: CONSTRAINT table_column_2자리제약조건종류 (*권장*)
- NOT NULL       :   table_column_nn
- UNIQUE           :   table_column_uk
- PRIMARY KEY  :   table_column_pk
- FOREIGN KEY  :   table_column_fk
- CHECK             :   table_column_ck
```  

제약조건 예시

```sql
CREATE TABLE department2(
    deptno NUMBER(2),  -- 여기서 작성해도 무관하다.
    dname VARCHAR2(15),
    loc VARCHAR2(15),

    CONSTRAINT department2_deptno_pk PRIMARY KEY (deptno)
);
```

-  USER_CONSTRAINTS 데이터 사전  

*특정 테이블의 제약조건 확인 (어떤 컬럼에 제약조건이 설정되어 있는지 확인불가)  
제약조건 타입(CONSTRAINT_TYPE 컬럼):  
P: PRIMARY KEY, R: FOREIGN KEY, U: UNIQUE,  
C: NOT NULL, CHECK (NOT NULL 제약조건은, NULL 값을 체크하는 조건으로 처리)*
  
USER_CONSCOLUMNS : 제약조건을 확인하는 용도  
