# View

1. *데이터를 선택적으로 보여줄수 있다.*
2. *데이터에 대한 접근을 제한할 수 있다.*
3. *테이블 컬럼중 보안과 관련된 민감한 데이터를 가진 컬럼에 대한*
    
    *접근제한이 가능하다.(보안강화)*
    
4. *검색을 위한 복잡한 쿼리를 단순쿼리로 변경, 일반적으로 조인쿼리문은*  
    *복잡성을 가지며 매번 필요시, 같은 조인쿼리를 사용하지 않고 뷰로*  
    *작성한다.*  

### 단순 View (= Simple View)

1. *하나의 기본 테이블(Base table) 에 대해 정의한 View*
2. *By defaujlt, View 에 대해 DML 문장 실행 가능*
3. *View 에 대한 DML 문장의 처리결과는, 실제 기본테이블(Base table)에 반영됨*
4. *새로 생성되는 View에 대해서 별칭(Alias)를 사용하지 않으면, 기본테이블(Base table)의 컬럼명을 상속하거나 서브쿼리(Sub-query)의 SELECT절에 기술된 컬럼별칭(column alias) 상속*
  
  
### 복합 View (= Complex View)

1. *2개 이상의 기본테이블(Base table)에 대해 정의한 뷰*
2. *2개 이상의 테이블을 Join해서 사용할 경우, 뷰로 생성*

```sql
GRANT CREATE VIEW TO scott; -- 권한부여

CREATE OR REPLACE VIEW emp_view AS
SELECT
    empno,
    ename,
    d.dname,
    d.deptno
FROM
    emp e JOIN dept d
    ON e.deptno = d.deptno       
WHERE
    e.deptno = 20;

SELECT *  -- 조회
FROM emp_view;
```

접근제한 하기

```sql
-- 보안강화
-- 급여 접근제한
CREATE OR REPLACE VIEW emp_view2 AS
SELECT   -- salary 제외
    empno,
    ename,
    job,
    mgr,
    hiredate,
    comm,
    deptno
FROM
    emp;
```

Complex View

*복잡한 쿼리의 결과를 단순한 쿼리로 변경이 가능하다.*

```sql
CREATE OR REPLACE VIEW complex_view AS
SELECT
    t2.department_name AS 부서명,
    count(t1.employee_id) AS 인원수
FROM
    employees t1,
    departments t2
WHERE
    t1.department_id = t2.department_id             -- 조인조건
GROUP BY
    t2.department_name;
```

WITH CHECK OPTION 제약조건

*WHERE 조건을  만족하는 데이터만, INSERT / UPDATE 가능하도록 제약하는 것 이다.*

```sql
-- 30번 부서의 사원만 변경(DML) 가능하도록 제약조건 설정
-- WITH CHECK OPTION 이용한 뷰(view) 생성
CREATE OR REPLACE VIEW emp_view6 AS
SELECT
    empno,
    ename,
    sal,
    deptno
FROM emp
WHERE deptno = 30
WITH CHECK OPTION;
```

WITH READ ONLY 제약조건

*뷰에 대한 DML 작업을 불가능하게 하며 View를 통한, 어떠한 기본 테이블(Base table) 변경도 불가능*

```sql
CREATE OR REPLACE VIEW emp_view6 AS
SELECT
    empno,
    ename,
    sal,
    deptno
FROM emp
WITH READ ONLY;
```

View DROP

*기본 테이블(Base table) 손실 없이 삭제한다.
View의 삭제 --> 곧, USER_VIEWS 데이터 사전에 저장된 TEXT 컬럼에 저장되어 있는,* 

*서브쿼리의 삭제*

```sql
-- View 삭제
DROP VIEW emp_view6;
```
