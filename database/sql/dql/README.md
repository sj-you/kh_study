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
