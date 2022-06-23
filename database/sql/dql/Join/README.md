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
