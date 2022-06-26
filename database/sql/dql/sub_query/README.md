# sub-query (부속질의)
    
*서브쿼리는, 하나의 SELECT 문장 만으로 원하는 데이터를 조회할 수 없을 떄 사용하는 방법 이다.*  
  
주의사항 : 메인쿼리가 한개의 연산자를 반환하는지 아니면 여러개를 반환하는지 파익이 필요.  

```sql
SELECT select_list -- 메인쿼리
FROM 테이블
WHERE 컬럼명 연산자 (
  SELECT select_list FROM 테이블 -- 서브쿼리
);
```

- 상관 부속질의  

  *서브쿼리(=부속질의)의 단독 수행이 불가능한 경우  
  **메인쿼리의 데이터가 있어야 실행가능한 경우**로,  
   메인쿼리가 먼저 수행되고, 차례대로 서브쿼리가 수행됨  
  메인쿼리의 결과가 서브쿼리에 전달되어, 서브쿼리 수행*  

- 비상관 부속질의  

  *서브쿼리(=부속질의)의 단독 수행이 가능한 경우로,  
  **서브쿼리가 먼저 수행된 다음에, 메인쿼리가 수행**됨  
  서브쿼리의 결과가 메인쿼리에 전달되어 실행됨*  


- 단일행 sub-query  
  
  ```sql
  -- 단일행
  SELECT
    last_name,
    salary,
    ( SELECT avg(salary) FROM employees) AS 평균급여
  FROM
    employees
  WHERE
    salary >= (   
        SELECT avg(salary)          -- 단일 행 서브쿼리 : 평균 월급여 반환												        -- 메인쿼리로 반환  
        FROM employees              -- 메인쿼리로 반환
    );
  ```

- 복수행 sub-query  
  
  ```sql
  -- 복수행
   SELECT         -- 부서별로 가장 많은 월급여를 받는 사원정보 조회
      last_name,
      department_id,
      salary
  FROM
      employees
  WHERE
      (department_id , salary) IN (
          SELECT department_id, max(salary)
          FROM employees
          GROUP BY department_id
      )
  ORDER BY
      2 ASC;
  ```  

  IN  

  *메인쿼리와 서브쿼리가 IN 연산자로 비교수행. 서브쿼리 결과값이 복수 개인 경우에 사용*  

  ```sql  
  SELECT
      last_name,
      salary
  FROM
      employees
  WHERE
      salary IN (
          SELECT salary
          FROM employees
          WHERE last_name IN ('Whalen', 'Fay')  -- 'Whalen', 'Fay' 의 월급여
      );
  ```

  ALL  

  *서브쿼리에서 > 또는 < 같은, 비교 연산자를 사용하고자할 때 사용.*   
  *검색조건의 모든 값이 일치하면 참.*    

  ```sql
  SELECT                -- 직책이 IT_PROG인 사원의 월급보다 *작은* 사원 정보 조회
      last_name,        
      department_id,
      salary
  FROM
      employees
  WHERE
      salary < ALL (       -- 복수 행 비상관 서브쿼리: 직책이 IT_PROG인 사원의 월급 반환
          SELECT salary    -- 메인쿼리로 결과값 전달
          FROM employees   -- 급여가 낮은 기준
          WHERE job_id = 'IT_PROG'
      );
  ```

  ANY ( >: 최소값보다 큰 | <: 최대값보다 작은)  

  *서브쿼리에서, > 또는 < 같은 비교 연산자를 사용하고자 할 때 사용.*   

  *검색조건이 하나라도 일치하면 참.*  

  ```sql
  -- ANY
  -- 직책이 IT_PROG인 사원의 *최소 월급여보다 큰* 사원 정보 조회
  SELECT
      last_name,
      department_id,
      salary
  FROM
      employees
  WHERE
  -- 결과적으로, 복수행 서브쿼리가 반환한 모든 값 중, *최소값 보다 큰* 사원 필터링
      salary > ANY(
          SELECT salary
          FROM employees
          WHERE job_id = 'IT_PROG'
      );
  ```

  EXISTS  

  *서브쿼리의 반환값이 존재하면, 메인쿼리를 실행하고, 반환값이 없으면 메인쿼리를 실행하지 않음.*  

  ```sql
  --EXISTS
  SELECT
      last_name,
      department_id,
      salary,
      commission_pct
  FROM
      employees
  WHERE
      EXISTS (
          SELECT employee_id
          FROM employees
          WHERE commission_pct IS NOT NULL  -- 리턴값 존재 : 메인쿼리 실행 
          --WHERE 1=2                       -- 리턴 불가 : 메인쿼리 실행X
      );
  ```
