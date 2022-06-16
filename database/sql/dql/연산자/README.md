
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

- LIKE (패턴매칭연산자)  
    _지정한 패턴을 출력하는 연산자 이다._    
    % ≥ 0, _ = 1,    
    
  ```sql
  WHERE LAST_NAME LIKE 'J%';            -- J로 시작하는 직원 검색
  WHERE LAST_NAME LIKE '%ai%';          -- 중간에 ai가 들어가는 이름 검색
  WHERE LAST_NAME LIKE '%in';           -- in으로 끝나는 이름 검색
  WHERE LAST_NAME LIKE '_b%';           -- 두번째 문자가 b로 시작하는 이름 검색
  WHERE LAST_NAME LIKE '_____d';        -- 5번째 단어가 d로 끝나는 이름 검색
  ```
    
- 탈출문자

  *ESCAPE 문자를 지정한 후에, 특수 문자앞에 ESCAPE문자를 넣어준다.*  

  *이렇게 되면 ESCAPE문자 뒤에 있는 문자를 일반 문자로 인식하게되어, _(언더바)가 들어간 상품명을 검색하게 된다.*    

```sql
WHERE JOB_ID LIKE '%$_%' ESCAPE '$';   -- 직무 ID 안에 _가 들어있으면 탈출  
WHERE JOB_ID LIKE '%E___' ESCAPE 'E';  -- 직무 ID중 _뒤에 두개의 문자가 있어애 함  
```
    
- IS NUll 연산자  
    
  ```sql
  WHERE
       COMMISSION_PCT IS NULL;      --NULL값 조회
       COMMISSION_PCT IS NOT NULL;  --NULL값이 아닌것
  ```  
    
- 연산자의 우선순위    
    
  *( ) → 비교연산자 → NOT연산자 → AND연산자 → OR 연산자*    

```sql
-- 우선순위
SELECT
    LAST_NAME,
    JOB_ID,
    SALARY,
    COMMISSION_PCT
FROM
    EMPLOYEES
WHERE   
    (JOB_ID ='AC_MGR' OR JOB_ID = 'MK_REP')-- 3. 소괄호 없을시 OR가 나중에 실시
    AND COMMISSION_PCT IS NULL -- 2.          -- () 없을시 ID만 일치시 출력
    AND ( SALARY BETWEEN 4000 AND 9000) -- 1. -- () 없을시 순서  

```
