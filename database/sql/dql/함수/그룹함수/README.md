# 그룹 함수  
_GROUP BY_  
  
    ```
    - **주의사항**
    - GROUP BY뒤에, column alias or index 사용 불가하다
    - GROUP BY뒤에 명시된 컬럼은 SELECT절에 그룹함수와 사용 가능
    - ORDER BY절의 다중정렬과 비슷하게, 다중그룹핑 가능
    - WHERE 절을 사용하여, 그룹핑하기 전에, 행을 제외시킬 수 있다.
    - HAVING 절을 사용해, 그룹핑한 후 행이아니라 그룹을 제외할수 있다.
    - WHERE 절에는 그룹함수를 사용할수 없다.
    - NULL도 생성할수 있다.
    ```

- SUM (그룹처리 함수)

    ```sql
    SELECT  
        sum(DISTINCT salary),
        sum(ALL salary),
        sum(salary)
    FROM
        employees;
    ```

- AVG(집계함수)  
   
    _평균을 구해준다_  

    ```sql
    -- AVG
    SELECT
        sum(salary),
        avg(salary)
    FROM
        employees;
    ```

- MIN / MEX  
  
    _최대/최소값을 구한다_

    ```sql
    -- MIN / MEX
    SELECT
        MIN(salary),
        MAX(salary)
    FROM
        employees;
    ```

- COUNT(행의 개수를 카운트 한다)  

    ```sql
    -- COUNT

    SELECT
        count(last_name),
        count(commission_pct) -- NULL 제외 후 카운트
    FROM
        employees;
    ```

- HAVING ( GROUP BY 이후 조건식)  
  
    *GROUP BY가 만들어낸 성질을 이용해 조건식을 작성한다.*  
  
    ```sql
    -- 직원수 
    SELECT
        department_id,
        count(employee_id)
    FROM
        employees
    GROUP BY
        department_id
    HAVING
        count(employee_id) >= 6;  -- 6명 이상인 그룹 설정
    ```  
