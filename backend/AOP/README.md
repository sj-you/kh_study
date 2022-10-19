# AOP (Aspect-Oriented Programming)

*관점 지향 프로그래밍*

e concerned about ~ 에 대해서 걱정하다.

Apect => 구현해야할 핵심비지니스 로직은 아니지만,
개발할 때의 "(횡단)관심사"(cross-concern)를 의미

### Target

*핵심 비지니스 로직이 구현된 서비스 객체*

*(@Service, 비지니스계층의 서비스) ==> 관심사들을 적용할 대상*

### JointPoint

*Tatget 객체가 가지고 있는 메소드들 (예 : tranfer메소드 - 계좌이체)*

### Advice

*횡단관심사(Cross-Concern)을 실제 구현한 기능 ( 예 : 트랜잭션 처리 )*
