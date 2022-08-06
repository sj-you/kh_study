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

### HTTP method

*하나의 from 양식의 데이터를 지정된 서버(action속성의 값) 프로그램에 보내는 방식을 의미한다. 대표적으로 get 과 post가 있다.*

### get

*사용자가 입력한 데이터를 첫행에  (?) 뒤에 요청 파라미터와 그 값을 전송하며 이것을 QueryString 이라고 한다. (문자열 길이제한 255)*

### POST

*폼 데이터를 별도로 첨부하여 서버로 전달하는 방식으로*

*POST 방식의 HTTP 요청에 의한 데이터는 쿼리 문자열과는 별도로 전송한다.*

*따라서 데이터의 길이에 대한 제한도 없으며, GET 방식보다 보안성이 높다.*

 

### 파일 업로드

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


---

### all form

```html
<form accept="http://localhost:8080/serverProgram" method="post">
    1. search: <input type="search" name="keyword"><br> <!--검색기능 --> 
    2. tel: <input type="tel" name="tel" pattern="[0-9]{3}-[0-9]{4}-[0-9]{4}" 
            placeholder="000-0000-0000"><br>  <!--전화번호 --> 
    3. url: <input type="url" name="url"><br>  <!--url --> 
    4. email: <input type="email" name="email"><br>  <!-- E-mail --> 
    5. date: <input type="date" name="today"><br>  <!-- 년/월/일 -->
    6. month: <input type="month" name="month"><br>  <!-- 년/월(입력가능) -->
    7. week: <input type="week" name="week"><br>  <!-- 년/주 -->
    8. time: <input type="time" name="now"><br>  <!-- 시간 설정(시:분) -->
    9. datetime-local <input type="datetime-local" name="localDT"><br>  <!-- 위치 날자 시간 -->
    10. number: <input type="number" name="age" min="0" max="120"><br>  <!-- 숫자 -->
    11. range: <input type="range" name="height" min="50" max="300"><br>  <!-- 범위값 -->
    12. color: <input type="color" name="color"><br>  <!-- 색상 조정 -->
    13. img: <input type="image"src="https://picsum.photos/id/684/200/200"
                name="myImage"><br><!-- img(submit) -->
    14. textarea: <textarea name="lines" cols="30" rows="10"></textarea><br><!-- text 양식 크기 --> 
    15. fieldset: <fieldset>
                    id: <input type="text" required>
                    pw: <input type="text">
                    </fieldset><br> <!-- text 양식 크기 -->
    16. datalist: 
                    My browser: <input list="browser" name="MyBrowser">  
                    <datalist id="browser">
                        <option value="Chrome"></option>
                        <option value="Edge"></option>
                        <option value="asd"></option>
                    </datalist><br><!-- 선택입력(콤보박스) -->
    17. progress: <progress max="100" value="30" name="currprog"></progress> <br>
    18. meter: <meter max="100" value="30" name="meter" ></meter><br><!-- 측량값 -->
    <!-- required 입력시 필수입력 -->

    <p></p>

    <input type="submit" value="전송">

</form>
```
