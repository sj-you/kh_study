# JSON


---

Java Object → JSON

```java
// Java Object -> JSON String
		
// 1. 객체 생성
Foo obj = new Foo();
obj.setId(100);
obj.setName("Sangjun");

log.info("\t+ obj : {}", obj);

// 2. JSON 으로 변환
Gson gson = new Gson();

String json = gson.toJson(obj);
log.info("\t+ json : {}", json);
```
