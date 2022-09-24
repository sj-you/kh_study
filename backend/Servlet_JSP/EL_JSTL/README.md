# EL(Expression Language)

### EL 변수

1. EL의 내장객체
2. 4개의 공유영역에 바인딩 되어있는 공유속성명
3. JSTL의 문법상, 만들어지는 변수

- EL언어의 문법: ${ EL변수 }  
- 그럼, EL변수란 무엇인가? 무엇이 EL변수로 지정가능한가?  
(1) 4개의 공유영역에 바인딩 되어있는 공유속성명 (***)
이거야 말로, 진짜 EL스펙상 나오는 EL변수이다.  
(2) EL의 내장객체  


### 내장객체

![image](https://user-images.githubusercontent.com/88135939/192012215-9fb390d6-0a9b-497e-a60d-9446d45217a4.png)


만일, 특정 공유영역에 바인딩 되어있는 공유속성이,  
아래와 같은 다양한 타입의 객체라면, 어떻게 ${ } 문법으로 출력하는 방법
(1) "자바빈즈" 객체이면...  
${ 공유속성.프로퍼티명 } / ${ 공유속성명.getter메소드호출 }  
  
(2) Map 객체이면...  
${ 공유속성.KEY } / ${ 공유속성명.get(key) 메소드호출 }  
  
(3) 배열 객체이면...  
${ 공유속성[인덱스번호] }  
  
(4) List 컬렉션이면...  
${ 공유속성[인덱스번호] } / ${ 공유속성명.get(인덱스번호) 메소드호출 }  
  
(5) 사용자 정의 객체이면...  
${ 공유속성.값을반환하는메소드호출 }  


# JSTL (JSP Standard Tag Livrary)

### Core

*JSTL Core 라이브러리는 JSTL에서 기본적이고 핵심적인 기능들을 구현해 놓은 라이브러리
이다. 예를 들어 문자열 출력, if문, for문과 같은 제어문과 같은 기능이 포함된다.*

# <c:choose>

> <c:choose>는 자바의 Switch문과 비슷한 역할을 합니다.
> 

# <c:when>

> case와 같은 역할을 하는것은 <c:choose>안의 <c:when>태그 입니다.
> 

# <c:otherwise>

> default문 같은 역할을 사용하고 싶으면 <c:shoose>태그 안에 <c:otherwise>태그를 사용합니다.
> 

## 속성

> <c:choose><c:otherwise> 는 속성을 사용하지 않습니다.<c:when>은 test 속성을 사용합니다.(필수)
> 

## c:forEach

```html
<%-- JSP 페이지에서 출력합니다. --%>
<c:forEach var="name" items="${nameList}" varStatus="status">    
	<p>${status.count} : <c:out value="${name}" /></p>
</c:forEach>
]
```
