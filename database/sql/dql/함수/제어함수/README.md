# 제어함수  

DECODE (조건처리 함수)

*조건이 반드시 일치하는경우, 동등비교 사용가능시  사용* 

```sql
-- DECODE(조건비교)
SELECT
    decode(
        salary,
            1000, salary * 0.1, -- if
            2000, salary * 0.2, -- elif
            3000, salary * 0.3, -- elif
            salary*0.4          -- else
    ) AS bonus
FROM
    employees;
```

CASE (비교문)

*범위비교가 가능한 경우에 사용*

```sql
SELECT
    salary,
    CASE 
        WHEN salary > 3000 THEN salary * 0.4
        WHEN salary > 2000 THEN salary * 0.3
        WHEN salary > 1000 THEN salary * 0.2
        ELSE salary * 0.1
    END AS 보너스
FROM
    EMPLOYEES;
```
