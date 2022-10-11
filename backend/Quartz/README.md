# Quartz

*Quartz는 다양한 Java 애플리케이션에 통합 될 수있는 작업 스케줄링 라이브러리입니다.*

1. Job : 수행시켜야 할 일(Task)  
인터페이스의 구현 클래스 작성

2. JobDetail   
위 1의 job을 포함한다.  
Identity : Job Name, Job Group  
Job에 전달할 데이터 설정  

3. trigger : 위 2에 대한 정보    
Identity : name, group 설정    
JobDetail 을 언제 시작시킬 건가 (실행주기 → 반복적 or 1회성)    

4. Scheduler  
Scheduling 된 Job을 실제 수행시키는 서버 프로그램  
Trigger(스케줄링) 를 등록  
JobDetail ( 실제 수행시킬 job ) 을 등록  
Trigger 대로 JobDetail을 수행  

5. Listener (3종류)    
Scheduler 자체의 Event Listenning  
Job Event Listenning  
Trigget Event Listenning  
