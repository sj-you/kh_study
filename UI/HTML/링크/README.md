# 링크

### 이미지 삽입하기

```html
<img src="https://picsum.photos/200/200"> 
```

*이미지는 저장이 되어있거나 링크를 사용해 표시 가능하다.*

*title 지정시 사진 이름이 지정된다.*

alt=”" : 이미지가 정상적으로 표현될수 없는 상황에서 대신 보여주는 문장이다.

### img 속성

![image](https://user-images.githubusercontent.com/88135939/182542720-40791d8b-b27b-4ef5-9398-e317119973f2.png)


### 비디오 삽입

*유뷰브에서 영상을 가져오려면 iframe을 복사하면 된다.*

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/lZCZ1M5e7Yc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

### 로컬영상 사용시

```html
<video width="320" height="240">
  <source src="파일경로" type="타입"> 

</video>
```

### 링크 걸기

```html
<h2>링크걸기</h2>

  <h3><a href="#">이동안함</a></h3>
  <h3><a href="http://daum.net">크라운 피시</a></h3>

  <h2>이미지에 링크걸기</h2>

  <a href="http://www.naver.com"><img src="img/lizard.jpg" width="100"></a>
  <a href="http://www.naver.com"><img src="https://picsum.photos/id/1025/600/400">
```

### 새로운 탭으로 링크열기

```html
<h2>새오운 탭으로 링크</h2>
  <h3><a href="http://www.facebook.com" target="_blank">1</a></h3>
  <h3><a href="http://www.naver.com" target="_blank">2</a></h3>
  <h3><a href="http://www.daum.net" target="_blank">3</a></h3>
```
