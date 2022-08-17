### 레이아웃

*웹 페이지에 박스, 텍스트, 이미지 등 HTML 요소를 배치하는 것을 말한다.*

- float 속성
    
    *웹 페이지에 요소를 왼쪽 또는 오른쪽에 배치하며 blook상태인 요소도 인라인처럼*  
    *처리가 가능하다.*  
    ![image](https://user-images.githubusercontent.com/88135939/184818757-39bec5b5-009a-4b44-8529-980e45ca41c5.png)

- clear 속성
    
    *float을 취소할수 있다.*
    
    ```html
    clear: both -> 오른쪽/왼쪽을 취소
    clear: left -> 왼쪽 취소
    clear: right -> 오른쪽 취소
    clear: none -> 기초값
    ```
    
    *flort을 유지하며 떠있지 못하게 한다. (*::after →*부모 컨탠츠 끝에서)*
    
    ```html
    .fix::after{
                content: '';
                display: block;
                clear: both;
            }
    ```
    
- position 속성
    
    *텍스트, 이미지 표 등의 요소를 웹 문서에 배치할 때 사용한다.*
    
    *정적 위치 : 블록 요소는 위에서 아래로 쌓이고, 인라인 요소는 같은 줄에 순서대로 배치*
    
    ![image](https://user-images.githubusercontent.com/88135939/185072491-89673c59-44f5-43bf-a317-f27e3061047b.png)

    
- z-index
    
    *한 요소 위에 다른 요소를 쌓을 때 사용하며 속성값이 작을수록 뒤로간다.*
    
    ![image](https://user-images.githubusercontent.com/88135939/185072649-303c6e04-8085-466a-85a4-935129b0bffd.png)
