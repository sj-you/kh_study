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
