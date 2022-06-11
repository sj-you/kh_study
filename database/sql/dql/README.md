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
