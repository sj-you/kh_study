
# 연산자
  
- 연결연산자 **( || )**

  ```sql
  SELECT column1 || column2 FROM table;    -- 컬럼1 과 컬럼2 를 이어준다.

  -- 문자열 + 숫자
  SELECT LAST_NAME || SALARY AS "이름 월급" FROM EMPLOYEES;
  ```
  Oracle 자동형변환 이 발생한다 : _숫자 ←→문자열_
      
- 비교연산자  
   _SQL에서의 동등비교 연산자는 자바와 다르게 = 이다._  
   _비 동등비교 연산자의 종류는 3가지가 있다 ( =! <> ^= )_      
    
  
- BETWEEN 연산자 (범위 연산자)    
    _아래 예제는 연봉이 7000 ~ 8000사이인 직원을 조회._  
    
    ```sql
    		-- 2. BETWEEN
    SELECT 
        EMPLOYEE_ID,
        LAST_NAME,
        SALARY,
        HIRE_DATE
    FROM 
        EMPLOYEES
    WHERE
        SALARY BETWEEN 7000 AND 8000;
    ```  
    
- IN (집합연산자)  
    _아래의 예제는 id 가 아래의 value인 값을 조회한다._  
    
    ```sql
    SELECT
        employee_id,
        last_name,
        salary,
        hire_date
    FROM 
        employees
    WHERE
        employee_id IN (100, 200, 300);
    ```
    
    *중복을 허용하지 않고 순서를 보장하지 않는다.*
    
- 논리연산사 (AND, OR, NOT)
    1.  AND : 그리고
    2.  OR : 또는
    3.  NOT : 부정
