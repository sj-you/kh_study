# 박스모델


*박스 형태로 된 모든 HTML 요소이며 경계선(border) , 마진(margin), 패딩(padding)*

*지정이 가능하다.*

```html
boder: 예시의 청색 경계선 등을 그리는데 사용 (테두리)
      - solid (실선)
      - double (이중실선)
      - dotted (점선)
      - dashed (줄 선)
padding: 경계선 내부의 콘텐츠와의 간격을 의미한다.
      - padding의 속성값 순서는 상, 우, 하, 좌 이다.
margin: 경계선 외부의 간격을 의미한다. (겹치는 영역이다)
      - width / height : 너비, 높이
      - 값을 지정하지 않아도 기본으로 값이 생기는데 
        필요 없을시 0으로 지정해준다.
```
![image](https://user-images.githubusercontent.com/88135939/183874912-ba3a50a9-2d38-431e-9f45-2635411b534e.png)
![image](https://user-images.githubusercontent.com/88135939/183874981-938cb136-6397-40e1-8c61-9bfb0c4eb3bf.png)

### border-style  
![image](https://user-images.githubusercontent.com/88135939/184112989-73fbcda6-1c95-4480-b07b-4ba54fb04efc.png)
  
  
### border-radius (둥근 모서리)  
*테두리의 모서리를 둥글게 해준다.*  
![image](https://user-images.githubusercontent.com/88135939/184113062-cc437673-c978-4e5b-9cb3-b918bd1edad8.png)


### border-style  
![image](https://user-images.githubusercontent.com/88135939/184297658-9ea5f3f0-f3bb-4c39-9a87-9e4567a9cc1d.png)
 
### border-radius (둥근 모서리)    
*테두리의 모서리를 둥글게 해준다.*    
![image](https://user-images.githubusercontent.com/88135939/184297753-8a1d19dc-581a-49ef-ae83-31eaefca4b70.png)


### box-shadow
*박스에 그림자 효과를 적용한다.*  
![image](https://user-images.githubusercontent.com/88135939/184297869-a5a3d39a-735b-448e-93ed-5eb857d8ce26.png)
*수평그림자(h-shadow) : 그림자 수평 거리 지정*

*수직그림자(v-shadow) : 그림자 수직 거리 지정*

*그림자흐림(blur) : 그림자의 흐림 정도 지정*

*그림자색생(color) : 색상 지정*

*삽입효과(inset) : 박스 외부로 표현되는 그림자를 박스 안쪽으로 표현*
