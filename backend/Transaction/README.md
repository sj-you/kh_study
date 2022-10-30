# 트랜잭션(Transaction, TX)

### 종류(2가지)

1.  분산 TX (== Global TX): 한 요청처리에 2개 이상의 연결
(Connections)를 사용하여 SQL처리를 하는 트랜잭션
- 동일한 DB에 2개이상의 연결(JDBC Connection)들을 사용
- 각 연결(JDBC Connection)마다, 각각 다른 DB를 사용
- 개발자가 직접 TCL사용 불가!!!(**TX 관리자**가 대신 수행)
- 스프링은 @Transactional 어노테이션으로 TX관리
- 2PC 사용(완전하지 않음): 2-Phase Commit (2PC)  
예: 2개의 데이터소스(각각 연결된 DB가 틀림)사용  
- phase: 현재 분산TX에 참여한 각각의 데이터소스에게
물어봄(Commit할 준비가 되어있는지)
