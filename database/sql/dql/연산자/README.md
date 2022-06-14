
# 연산자
  
- 연결연산자 **( || )**

  ```sql
  SELECT column1 || column2 FROM table;    -- 컬럼1 과 컬럼2 를 이어준다.

  -- 문자열 + 숫자
  SELECT LAST_NAME || SALARY AS "이름 월급" FROM EMPLOYEES;
  ```
  Oracle 자동형변환 이 발생한다 : _숫자 ←→문자열_
      
