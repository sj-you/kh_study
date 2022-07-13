
    
#TCL - Transaction Control Language (트랜잭션 제어 언어)

*COMMIT, ROLLBACK, SAVEPOINT*

### TCL (Transaction Control Language)

---

Transaction (트랜잭션)
*1. DB의 논리적인 작업단위
2. 분리될 수 없는, 한개 이상의 DB조작을 의미
3. 하나의 트랜잭션에는, 한 개 이상의 SQL문장이 포함가능*
4.  *트랜잭션 대상 SQL문장은, "DML" 문임(***)*

```
*오라클에서 발생되는, 여러 개의 작업들을, 하나의 작업처럼
처리해야 하는 경우에, 트랜잭션이 필요!!! (예: 계좌이체)
트랜잭션 제어 명령어(TCL) 제공: (** All or Nothing **)***
```

- **COMMIT (All)**
*DML문에 의해 실행되었으나, 아직 저장되지 않은 모든 데이터를  
데이터베이스에 저장하고, 현재의 트랜잭션 종료시킴.*  
****
- **ROLLBACK [TO SAVEPOINT savepoint] (Nothing)**     
*저장되지 않은 모든 DB변경사항 취소하고, 현재의 트랜잭션을  
종료시킴. 트랜잭션 시작 이전의 상태로 복구.  
TO SAVEPOINT 키워드 사용하면, 지정된 SAVEPOINT까지만  
DB변경사항 취소가능 (Partial Rollback)*  
****
- **SAVEPOINT**  
*진행중인 트랜잭션을, 특정이름으로 지정(like 책갈피)  
지정된 이름의 상태로, 실행된 DML 작업의 취소가능  
 (Partial Rollback)  
락 경합(Race Condition)으로 인한, 데드락(Dead Lock) 발생가능  
락 경합으로 인한 무한대기는, 오라클의 성능을 대폭 감소시키는 원인  
매우 주의해야 함 ()*  
