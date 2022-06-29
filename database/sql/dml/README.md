
# DML

> *INSERT, DELECT, UPDATE, MERGE*  
> *INSERT / INSERT ALL / INSERT FIRST*  
> *INSERT-SELECT / CTAS*

- BEGIN - END

  *하나의 트렌젝션 안에 여러개의 DML문장을 실행하기 위해 사용한다.*

  *TX Boundary(범위)를 지정할떄 사용한다. [ TX Unit( 한개의 DML문 ) ]*

  *COMMIT을 하면 저장하며 ROLLBACK을 수행하면 변경내역을 취소한다.*

### INSERT
    
- INSERT   
*테이블에 데이터를 저장하기 위한 문장이다.*    
    
 ```sql
 -- 기본문법
 INSERT INTO 테이블명 [ (컬럼명1, 컬럼명2, ...)]
 VALUES ( 값1, 값2, ...);
 ```

- 단일행 INSERT  
 *한번에 하나의 행을 테이블에 삽입한다.*

 ```sql
 BEGIN

     INSERT INTO dept(deptno, dname, loc)
     VALUES ( 50, '개발', '서울');

     INSERT INTO dept
     VALUES (60, '인사', '경기');

     INSERT INTO dept(deptno, dname)
     VALUES(70, '인사'); -- NULL값이 들어가지만 명지적으로 표시하는게 좋다.

     -- ROLLBACK (이전으로 돌림)
     COMMIT; -- 영구저장 
 END;
 ```

- 다중행 INSERT  
 *한번에 여러개의 행을 테이블에 삽입한다.*  
  *VALUES 절 대신에, 서브쿼리(= 부속질의) 사용하고서브쿼리를 사용하여,*   
 *기존 테이블의 데이터를 복사한 후에, INSERT 문으로 새로운 행 생성.*  

 ```sql
 --Basic Syntax)
 INSERT INTO 테이블명 [ (컬럼명1, 컬럼명2, ..., 컬럼n) ]
 Subquery;
 ```

- 복사 ( 제약조건은 제외)  

 ```sql
 CREATE TABLE mydept
 AS
 SELECT * FROM dept
 WHERE 1 = 2;   -- 기존 스키마만 복사
 ```

 - INSERT ALL  
 *하나의 INSERT문장으로 한번에 한 개 이상의 테이블에, 여러개의 행을 저장*  

 ```sql
 INSERT ALL
  [WHEN 조건식 THEN]
  INTO 테이블1 VALUES (컬럼명1, 컬럼명2, ..., 컬럼명n)
  [WHEN 조건식2 THEN]
  INTO 테이블2 VALUES (컬럼명1, 컬럼명2, ..., 컬럼명n)
  ..
  [WHEN 조건식n THEN]
  INTO 테이블n VALUES (컬럼명1, 컬럼명2, ..., 컬럼명n)
  Subquery;
 ```

 WHEN 절은 생략가능 ** (= 무조건 INSERT ALL 문)  
 *WHEN절이 있는 경우, 조건식이 참일 때에만, 지정된 테이블에  
 서브쿼리의 결과가 INSERT 됨*  

 - 조건 INSERT ALL   

 *VALUES 절에 사용된 컬럼명과 Subquery에서 사용된 컬럼명이 반드시 동일해야 한다.*

 ```sql
 INSERT ALL
     WHEN sal > 3000 THEN
         INTO myemp_hire2 VALUES (empno, ename, hiredate, sal)
     WHEN mgr = 7898 THEN
         INTO myemp_mgr2 VALUES (empno, ename, mgr)
 SELECT
     empno,
     ename,
     hiredate,
     sal,
     mgr
 FROM
     emp;
 ```

 - 조건 INSERT FIRST  
  
 *기존 테이블을 이용하여, 새로운 테이블 생성 (CTAS)*  
  *CTAS: 기존 테이블 스키마 복사 시, NOT NULL 제약조건을 제외한,*   
  *그 외 제약조건은 복사되지 않음.*  

 ```sql
 INSERT FIRST
     -- sal = 800 인 사원은, 아래 두 WHEN 절의 조건식을 모두 만족.
     -- 이때, 첫번째 WHEN절에서만 INSERT가 수행되고,
     -- 두번째 WHEN절은 설령 조건이 참이어도, INSERT 수행되지 않음.
     WHEN sal = 800 THEN     -- 1st. condition
         INTO myemp_hire3 VALUES (empno, ename, hiredate, sal)

     WHEN sal < 2500 THEN    -- 2nd. condition
         INTO myemp_mgr3  VALUES (empno, ename, mgr)

     SELECT
         empno,
         ename,
         hiredate,
         sal,
         mgr
     FROM
         emp;
 ```
