


# DCL - Data Control Language (제어)

*사용자 계정을 CRUD하고 다양한 DB객체에 대전 접근권한 설정이다.*

*GRANT, CREATE USER, ALTER USER, DROP USER*

*Oracle Cloud 버전부터, 새로운 사용자(계정 스키마) 생성*

```sql
GRANT connect, resource, unlimited tablespace 
TO scott IDENTIFIED BY Oracle12345678;
```

*새롭게 생성된 사용자 계정이 데이터 테이블을 저장할 데이블스페이스와 ORDER BY 절에 의한 정렬 등에 필요한 임시 테이블스페이스를 지정해야 한다.*

```sql
ALTER USER scott DEFAULT TABLESPACE users;
ALTER USER scott TEMPORARY TABLESPACE temp;
```

*기존 사용자의 암호를 변경하는 문장이다.*

```sql
ALTER USER scott IDENTIFIED BY Oracle123;
```

*GRANT 문을 통해, 필요한 권한/역할 등 TO에 지정한 계정에 부여한다.*

```sql
GRANT create view, create synonym, create sequence 
TO scott;
```

```sql
GRANT select, update, insert, delete ON emp TO hr;
```

*아래 문장으로 비밀번호도 변경하고, 계정을 잠그거나(lock)/풀거나(unlock) 가능*

```sql
ALTER USER scott ACCOUNT LOCK;		-- 지정된 계정 잠그기(lock)
ALTER USER scott ACCOUNT UNLOCK;		-- 지정된 잠긴계정 풀기(unlock)
```

```sql
ALTER USER scott
IDENTIFIED BY Oracle123
ACCOUNT UNLOCK/LOCK;
```
