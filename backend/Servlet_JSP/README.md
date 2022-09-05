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
