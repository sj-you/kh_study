# CSS
HTML을 보조하여 웹 페이지, 글자 등을 도와주는 요소이다.

- CSS의 우선순위
    
    <aside>
    💡 인라인 → 내부 → 외부 → 브라우져 기본
    
    </aside>
    
    *만약 하나의 요소에 스타일 시트가 중복되면 마지막에 설정된 값이 적용.* 
    

```css
<style>
        table, tr, th, td{\
						/* 각 테이블 경계에 선 그리기 */
            border: solid 1px rgba(61, 128, 7, 0.842);
						/* 각 셀의 경계선을 여백으로 합침 */
            border-collapse: collapse;
            /* 안쪽여백 */
            padding: 8px;
        }
</style>
```

- 태그 선택자
    
    *태그의 영역을 선택하고 이후에 오는 CSS 명령을 해당 영역에 적용<p>*
    

- id 선택자
    
    *웹 페이지에서 유일무이한 단 하나의 특정 영역을 지정하여 CSS 명령 적용하며,*
    
    *id명 앞에 샵(#) 을 붙여야 한다.*
    

- 클래스 선택자
    
    *두 군데 이상의 특정 영역 지정하여 동일한  CSS 적용하고,*
    
    *클래스명 앞에 점(.) 을 붙인다.*  
    
- CSS reset
    
    *Layout 작업시 가장 처음에 해주는 스타일 작업으로 박스영역의 컨텐츠 영역만 살려서, 요소배치를 더 쉽게 하기 위해 한다.*
    
배경이미지 반복 

```html
<style>
    body{
        background-image: url("https://picsum.photos/200/200");
        background-repeat: no-repeat; <!--반복안함 -->
    }
    #button{
        margin: 325 0 0 60px;
    }        
</style>
```

- 외부 CSS 불러오기
    
    *<head> 안에 작성하면 된다.*
    
    !important : *강제로 적용한다.*
    
    ```html
    <link rel="stylesheet" href="css/01_css.css">
    ```
    

- 변이 효과
    
    ```html
    transition: all 1.5s linear 0.5s;
    ```
