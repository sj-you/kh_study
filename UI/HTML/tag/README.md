# Tag
테그는 크게 2가지의 종류가 있다

1. block-level Tag
    
    *하나의 태그가 뷰포트에 렌더링될 떄, 온전히 하나의 행 영역을 다 차지하는 태그* 
    
2. Inline-level Tag
    
    *시작 / 끝 태그 사이에 나온 컨텐츠를 표시할수 있을 만틈만의 공간을 치지하도록함*
    

<meta> : *이 테그는 메타데이터를 제공한다.*

<meta charset="UTF-8"> : *문자집합을 지정하는 것이다.*

content="IE=edge” : *만일 사용자가 IE로 접속할시 Edge로 재실행 하도록 설정.*

글 제목 만들기

```html
<h1>Sample01</h1>
<hr>
<h2>hello? I am Sangjun</h2>
<h3>하하하하</h3>
<h4>점점 작아진다고~~</h4>
<h5>어디까지 작아질까?</h5>
<h6>여기까지~!~</h6>
```

단락 나누기

```html
		<p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
    </p>
```

html special character 검색후 기호를 찾아볼수 있다.

<b> : 글자를 두껍게 표시하는 기능이다.

<br> : 줄봐굼을 해준다.

&nbsp; : 공백을 표현해준다.

- 목록 나누기
    
### 순서가 없는 목록  

*ul>li*n 을 입력시 n개의 li 자동으로 생성*

```html
<ul>
    <li>Lorem ipsum dolor sit amet.</li>
    <li>Lorem ipsum dolor sit amet consectetur.</li>
    <li>Lorem ipsum dolor sit.</li>
</ul>
```
    

### 순서가 있는 목록  

*ol>li*n 을 입력시 n개의 li 자동으로 생성*

```html
<ol>
        <li>Lorem ipsum dolor sit amet.</li>
        <li>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eum, esse!</li>
        <li>Lorem ipsum dolor sit amet consectetur.</li>
    </ol>
```
### tag 공통 적용 가능 속성
![image](https://user-images.githubusercontent.com/88135939/181699126-84646246-b79a-46f1-91c0-15e928e71877.png)
![image](https://user-images.githubusercontent.com/88135939/181699188-6c0e2e05-b70c-4844-80e8-762989ed40b7.png)  

  
### 웹 사이트간 이동
href : 연결하고자 하는 웹 사이트의 URL 지정

target : 링크를 클릭했을때 웹 사이트가 열릴 곳 지정

```html
_blank : 새로운 창으로 연다
_self : 현제 브라우저 창에 연다( 기본 )
_parent 부모 브라우저에 연다
_top : 전체에 연다.
```  

- 웹 사이트 간 이동
    
    href : 연결하고자 하는 웹 사이트의 URL 지정
    
    target : 링크를 클릭했을때 웹 사이트가 열릴 곳 지정
    
    ```html
    _blank : 새로운 창으로 연다
    _self : 현제 브라우저 창에 연다( 기본 )
    _parent 부모 브라우저에 연다
    _top : 전체에 연다.
    ```
    

- 정의형 목록
    
    *항목은 dt, 정의는 dd 테그를 이용한다.*
    
    ```html
    <dl>
        <dt>lodd</dt>
        <dd>- sdsd</dd>
        <dt>sdsdsd</dt>
        <dd>- sdsdsddd</dd>
    </dl>
    ```
    

- 임베디드 테그
    
    ![image](https://user-images.githubusercontent.com/88135939/182309628-1d2496c8-a406-4970-bc94-4064c0d374fc.png)
    

- <source>
    
    *여러 형식의 오디오 파일을 동시에 제공할 때 사용하고,*
    
    *재생에 적합한 파일이 없다면 마지막 문장을 출력한다.*
    

- <audio> 속성
    
    ```html
    controls : 재생 제어기 표시
    
    loop : 반복재생
    
    autoplay : 열림과 동시 실행
    
    muted : 음소거 시작
    
    preload : 사용여부 상관 없이 미리 다운로드
    ```
    

- <imbed>
    
    html 페이지 안에서 다른 프로그램을 구동시킨다,
    

- optgroup
    
    *그룹으로 묶어서 옵션을 지정할 수 있다*
    
    ```html
    <optgroup label="computer">
        <option value="1">Software</option>
        <option value="2">Robot</option>
        <option value="3">System</option>
    </optgroup>
    ```
    
- iframe
    
    다른 사이트나 HTML 문서를 불러올수 있다.
    
    ```html
    <body>
        <iframe src="br_p.html" frameborder="0"></iframe>
        <iframe src="http://www.w3.org" frameborder="0"></iframe>
    </body>
    ```
