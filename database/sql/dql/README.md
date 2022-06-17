# DQL(Data Query Language)  
  
- DQL은 데이터를 조회하는 쿼리로 실행순서가 정해져 있다.  ]

- DQL의 실행순서는 아래와 같다.  
  _FROM -> WHERE -> GROUP BY -> HAVING -> ORDER BY 이다._     
    
  작성예시
  ```sql
  SELECT FROM WHERE GROUP BY HAVING ORDER BY
  ex) SELECT SALARY FROM EMPLOYEES;
  ```
  
- 결과집합 (Result Set)  
  SELECT 실행을 하면 나오는 "결과들"을 의미한다.  
  
- 산술연산자 활용 가능하다( +,  -, *, / )

```sql
SELECT
    SALARY,
    SALARY + 100
FROM EMPLOYEES;
```  

- SYS.DUAL table  
  _의미가 없는 테이블을 뜻하며 FROM절을 생략할 수 없다는 제약때문에 등장했다._
- AS  
 _이름을 변경해서 보여주며 대문자나 띄어쓰기를 표현하려면 *“내용”* 을 입력해야 한다._
  
  
- NULL  
   _SQL 에서의 NULL은 결측치를 뜻한다. [결측치 : 아무것도 없다. && 무한대]_    
- NULL 값의 기본값 처리  
   _결측치 처리 : nvl함수를 사용하여 값이 NULL이면 지정한 기본값을 반환_  

  ```sql
    SALARY * 12 + **nvl(COMMISSION_PCT, 0)** AS 연봉
  ```
        
- 함수(Function)  
  _OOP언어의 “메소드”와 비슷하게 특정 기능을 수행하는 코드덩어리에 “이름”을 붙인것._      
  _대신 OOP와 다르게 함수는 어느 객체의 소속이란 개념이 없는 단독으로 존재하는 코드덩어리 이다._     
  
- **WHERE** : 1차 필터링 이라고 하며 뒤에 조건을 붙인다.  
  
- **DISTINCT** : 컬럼의 중복을 제외하고 보여준다.
    
  ```sql
  SELECT DISTINCT JOB_ID FROM EMPLOYEES;
  ```  
  
  
- 자동  형변환  
  _‘<NUMBER> <-> <CHARACTER> <-> <DATE> 간에는, 자동형변환이 됨!!! (*****)_  
  _따라서, 아래의 조건식은 <DATE> > <CHARACTER> 의 비교식으로 자동형변환에 의해, 당연히 비교가 가능해진다!_  
- 강제 형변환  
  _개발도구별 포맷 방식이 다르기 때문에 지정한다._  
  _자동형변환을 포기하고, 강제형변환 함수인 to_date()로 직접 DATE 타입으로 형변환시켜서, 비교하는 이유는 가독성 확보 이다._  
    

- ORDER BY    
  _정렬을 할떄 사용하는 것으로 기본은 ASC 이며 DASC로 지정할수 있다._  

  ```sql
  SELECT
      EMPLOYEE_ID,
      LAST_NAME,
      JOB_ID,
      SALARY
  FROM
      EMPLOYEES
  ORDER BY
      SALARY; -- 지정을 하지 않았음으로 ASC
  ```

  *다만 ORDER BY 를 이용할시 꼭 필요할떄만 하자 메모리를 많이 먹는다.*  

- 다중컬럼 정렬  

  ```sql
  -- 다중컬럼 정렬
  SELECT
      EMPLOYEE_ID,
      LAST_NAME,
      SALARY,
      HIRE_DATE
  FROM
      EMPLOYEES
  ORDER BY
      SALARY DESC, -- 급여
      HIRE_DATE;   -- 일자
  ```  

  *이전의 정렬결과를 깨트리지 않고 정렬한다. (급여로 정렬 후 일자로 정렬)*  

- ORDER BY 를 활용해 내림치순으로 정렬할때 NULL값이 가장 크다고 판단한다.  
    
  
  
  
