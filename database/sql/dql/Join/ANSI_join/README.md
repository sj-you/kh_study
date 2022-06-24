# ANSI Join *~~(OREACLE 사용자는 사용안함)~~*
    
Cross join (교차곱)

- 자연조인  
  동등조인에서 공통컬럼의 중복을 제거하며 사용할때 NATURAL JOIN 키워드를 사용

  ```sql
  SELECT
      last_name,
      department_id, -- 공통
      manager_id,    -- 공통
      department_name
  FROM
      employees NATURAL JOIN departments; -- 공통컬럼 중복제거 조인
  ```

  *다만 조인을 진행할시 대상과 같은 속성이여야 하는데 이름만 보고 조인하기 떄문에 엉뚱한 결과값이 나온다*  

- USING  
  
  *자연조인에서 발생햇엇던, 두 개 이상의 공통컬럼에 의해 발생가능한 엉뚱한 결과를 예방하기 위해, 명시적으로 조인할 컬럼을 지정하는 방식*  

  ```sql
  SELECT
      t1.last_name,
      t2.department_name,
      -- 공통컬럼은 식별자를 가질 수 없디
      department_id -- 공통컬럼
  FROM
      employees t1 INNER JOIN departments t2
      USING(department_id); // 공통컬럼 지정
  WHERE
      department_id = 90; -- 검색조건
  ```

- ON

  *Non-equal Join 이나, 임의의 조건으로 Join 할 경우에 사용*  
  *조인조건을 FROM에 작성하고  WHERE을 사용해 검색조건을 추가할수 있다.*  
  *범위를 구하기 위해선* *Non-equal Join 을 사용*   

  ```sql
  SELECT
      t1.last_name,
      t2.department_name,
      t1.department_id -- 공통컬럼
      -- department_id -- 공통 X
  FROM
      employees t1 INNER JOIN departments t2
      ON t1.department_id = t2.department_id  -- 조인조건
      AND t1.department_id = 90;              -- 검색조건 (가독성 저하)
  ```

- OUTER JOIN { LEFT | RIGHT | FULL }   
  
  *오라클의 outerJoin 과 같으며 차이점은 (+)를 어느 한쪽과 양쪽에 사용이 가능하다.*  

  ```sql
  SELECT 테이블1.컬럼 , 테이블2.컬럼
  FROM 테이블1 {LEFT | RIGHT | FULL} OUTER JOIN 테이블2
  ON 조인조건 | USING(컬럼)
  WHERE 검색조건 
  ```
