# from tag

*하나의 양식은 하나의 테그로 구성되어야 한다.*

*action 에 지정된 양식으로 전송*

```html
<form action="https://localhost:8080" method="get">
    아 이 디 : <input type = 'text' name="id"><br>
    비밀번호 : <input type = 'password' name="pw">       
</form>
```

### 데이터 전송

```html
<p></p>

<input type="submit" value="전송">
<input type="reset" value="초기화">
```

HTTP method

*하나의 from 양식의 데이터를 지정된 서버(action속성의 값) 프로그램에 보내는 방식을 의미한다. 대표적으로 get 과 post가 있다.*

get

*사용자가 입력한 데이터를 첫행에  (?) 뒤에 요청 파라미터와 그 값을 전송하며 이것을 QueryString 이라고 한다. (문자열 길이제한 255)*

POST

*폼 데이터를 별도로 첨부하여 서버로 전달하는 방식으로*

*POST 방식의 HTTP 요청에 의한 데이터는 쿼리 문자열과는 별도로 전송한다.*

*따라서 데이터의 길이에 대한 제한도 없으며, GET 방식보다 보안성이 높다.*

 

파일 업로드

*input type을 file로 설정하면 파일 첨부가 가능하다.* 

*(multiple 속성 사용시 여러개의 파일 첨부)*

```html
<form>
      파일 첨부 : <input type="file" name="uploadFile" multiple >
</form>
```

첨부파일 입력시enctype="multipart/form-data” 를 꼭 지정해야 한다

select (이메일 작성)

```html
<!-- form>(input+select>option*5) -->
<form method="get" enctype="application/x-www-form-urlencoded" action="http://localhost:8080/serverProgram">
    이메일 : <input type="text" name="email_id"> @

    <select name="email_addr">
        <option value="0">선택</option>
        <option value="1">naver.com</option>
        <option value="2">daum.net</option>
        <option value="3">gmail.com</option>
        <option value="4">hanmail.com</option>

    </select>
</form>
```
