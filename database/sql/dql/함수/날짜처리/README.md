# 날짜 처리 함수
    
NEXT DAY 함수(날짜 처리)

```sql
-- 날짜처리 함수 - NEXT DAY 
SELECT
    last_name,
    hire_date,
    next_day(hire_date, 'FRI'),
    next_day(hire_date, 6) -- 금요일(일요일부터 1 ~ 7) 출력
FROM
    employees
ORDER BY
    3 desc;
```

LAST_DAY 함수

```sql
-- LAST_DAY (지정 월의 마지막 날짜 변환)
SELECT
    last_name,
    hire_date,
    last_day(current_Date) -- 현재
FROM
    employees;
```

ROUND 함수(날짜 반올림)

```sql
-- ROUND(년도 또는 월 반올림)
SELECT
    last_name,
    hire_date,                -- 
    round(hire_Date, 'YEAR'), -- 년도 반올림(절반 이상일시) 월기분
    round(hire_date, 'MONTH') -- 월 반올림(절반 이상일시) 일기준
FROM
    EMPLOYEES;
```

*1월부터 6월은 해당 연도의 1월 1일을 반환하고 7월부터 12월은 다음 연도의 1월 1일을 반환한다.*

TRUNC

```sql
-- TRUNK (절삭)
SELECT
    last_name,
    hire_date,
    trunc(hire_date, 'YEAR'), -- 년도 이외 01.01
    trunc(hire_date, 'MOnTH') -- 년 월 제외 01
FROM
    EMPLOYEES;
```

자동형변환

```sql
-- 자동형변환 예
SELECT 
    last_name,
    salary
FROM
    employees
WHERE                 -- 자동형변환 (가독성 별로.)
    SALARY = '17000'; -- NUMBER(숫자) -> CHAR(문자열) <- date
```

TO_CHAR (문자로 변환)

```sql
SELECT
    to_char(sysdate, 'YYYY/MM/DD,(AM) DY HH24:MI:SS') as DT1,
    to_char(current_date, 'YYYY/MM/DD,(AM) DY HH24:MI:SS') as DT2
FROM
    dual;
```

*자동형변환이 가능하지만 가독성을 위해 명시해주자*

TO_NUMBER ( 숫자로 변환)

```sql
SELECT 
    to_number('123') + 100,
    '456' + 100,
    to_char(123) || '456',
    123 || '456'
FROM
    dual;
```
