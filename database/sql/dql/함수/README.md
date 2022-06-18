# 문자처리 함수  


  

> INITCAP : 첫글자를 대문자로 변환
> 
> 
> UPPER : 모든 글자를 대문자로 변경
> 
> LOWER : 모든 글자를 소문자로 변경
> 
> CONCAT : 두 문자열 연결
> 
> LENGTH : 문자열 길이 반환
> 
> INSTR :  문자열에서, 특정 문자열 위치(인덱스) 반환
> 
> SUBSTR : 문자열에서, 부분문자열(substring) 반환
> 
> REPLACE : 문자열 치환
> 
> LPAD : 문자열 오른쪽 정렬 후 왼쪽에 지정문자 채우기
> 
> RPAD : 문자열 왼쪽 정렬 후, 오른쪽 빈 공간 지정문자 채우기
> 
> LTRIM : 문자열의 왼쪽에서, 지정문자 삭제
> 
> RTRIM : 문자열의 오른쪽에서, 지정문자 삭제
> 
> TRIM : 문자열 왼/오/양쪽의 지정문자 삭제 (중간은 처리 못함)
> 

REPLACE (치환함수)

```sql
 -- 치환
SELECT
    replace('JACK and JUE', 'J', 'BL')
FROM
    dual;
```
