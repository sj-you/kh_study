# Servlet/JSP

### JSP

Web Application 규약

*Document Root 역할을 하는 폴더가 있어야 한다.  
위의 Document Root 역할의 폴더 밑에는 반드시 WEB-INF 가 있어야 한다.  
WEB-INF 폴더 안에는 web.xml 파일이 있어야 한다.*


### 핵심 Class

ServletConfig

```java
@Override
public void init(ServletConfig config) throws ServletException {
	log.trace("config({}) invoked.", config);
	
	String dirpath = config.getInitParameter("dirpath");
	String userid = config.getInitParameter("userid");
	
	log.info("\t+ dirpath: {}, userid: {}" , dirpath, userid);
	
	super.init(config);
} // init-config
```
### 공유 데이터 영역

*영역의 크기는 1~4 순이다.(1이 가장 크다)*  
![image](https://user-images.githubusercontent.com/88135939/188564631-a0e16143-f317-4486-aa2a-7068176a488c.png)

### Filter

 HTTP **요청과 응답을 변경**할 수 있는 **재사용** 가능한 클래스

 특징:

1. **객체** 형태로 존재
2. 클라이언트에서 오는 **요청(request)**과 **최종 자원** 사이에 위치하여, **클라이언트의 요청 정보**를 알맞게 변경 가능
3. **최종 자원**과 클라이언트로가는 **응답(response)** 사이에 위치하여, **최종 자원의 요청 결과**를 알맞게 변경 가능

```java
public void doFilter(ServletRequest req, ServletResponse res, FilterChain chain)
throws IOException, ServletException {
	// 여기에 코드 작성
	
	// 그 다음 필터로 넘겨준다.
	chain.doFilter(req, res);	// req에 대한 선처리와 res 에 대한 후처리를 제어하는 호출
} // doFilter
```
