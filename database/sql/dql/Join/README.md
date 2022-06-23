# JOIN
    
*필요한 데이터가, 여러 테이블에 분산되어 있을떄 여러 테이블의 공통된 컬럼을 연결시켜 검색하는 방법을 말한다.*

**Join 조건**

*합병이 가능해야 한다. (Union Compatible) —> 서로 성질이 동일해야 한다.*  
*즉 “참조무결성제약조건”을 가지는 두 테이블간 PK, FK를 이용한 조인을 의미.*  

    
  
세타Join : 두 릴레이션간 비교 조건에 만족하는 집합  
동등Join : 두 릴레이션간 같은 값을 가진 집합  
자연Join : 동등Join에서 중복을 제거  
  
  
    
- Catesion Product (카데시안 프로덕트)

*무의미한 조인으로 모든 조인에서 가장 먼저 발생하는 조인이자 기본이 된다.*  
*유요한 데이터로 사용하지 못하고 조인조건이 생략된 경우 사용*  

```sql
SELECT
    count(*)
FROM
    employees,
    departments;
```

- Equal Join (동등조인)

*두 테이블에서, 공통으로 존재하는 컬럼의 값이 일치하는 행들을 연결하여 데이터를 반환하며 일치하지 않는 데이터는 제외된다.*

```sql
SELECT
    last_name,

    employees.department_id,
    departments.department_id, 

    department_name
FROM
    employees,   -- 테이블 1
    departments  -- 테이블 2 
WHERE
    employees.department_id = departments.department_id; -- join
```

- 검색조건 추가
*조인조건을 우선 명시하고 나중에 검색조건을 명시하는 방법으로, 가동석을 향상*
- 테이블 별칭
    
    *테이블 별칭을 지정한 경우 반드시 별칭을 사용하여 참조해야 한다*  
    ```sql
    SELECT
        last_name,      -- 모호성이 없으므로 생략가능
        dept.department_name,
        emp.department_id
    FROM
        employees emp,
        departments dept
    WHERE
        emp.department_id = dept.department_id;
    ```  
    Non-equal Join (비 동등 조인)

*조인대상이 범위값으로 되어있는 경우*

```sql
-- 급여등급 Join
SELECT                      
    last_name,
    salary,
    grade_level
FROM
    employees e,
    job_grades g
WHERE
    e.salary BETWEEN g.lowest_sal AND g.highest_sal;
```

Self Join

*하나의 테이블만 사용하여, 자기자신을 조인하는 것을 의미.*

```sql
SELECT
    e.employee_id AS 직원사번,
    e.last_name AS 사원명,
    e.manager_id AS 관리자사번1,
    m.employee_id AS 관리자사번2,
    m.last_name AS 관리자명
FROM
    employees e,-- 사번
    employees m -- 관리자(복제)
WHERE
    e.manager_id = m.employee_id;
```

 Outer join ( Left or Right )

*동등조인에서 탈락한 튜플을 삽입하는 것을 말한다.*

*(+)를 사용할때 살리고자 하는 반대편에 배치한다.*

```sql
SELECT
    e.employee_id AS 사원번호,
    e.manager_id AS 관리자번호,
    e.last_name AS 사원명,
    m.last_name AS 관리자명
FROM
    employees e,
    employees m
WHERE
    e.manager_id = m.employee_id(+);  -- 사원에서 탈락한 사원 살리기
```
