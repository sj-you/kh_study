# Table

*테이블 제작시 헤드와 바디를 구분하여 작성한다.*  
*<tfoot> 으로 행도 구분해줘야 한다.*  

```css
<table>
	<thead>
      <tr>
          <th>출발</th>
			</tr>
	</thead>
	<tbody>
	</tbody>
</table>
```

```
<table> : 테이블 범위

<tr> : 하나의 행

<th> : 테이블 각 열의 제목

<td> : 열 제목의 나타내는 첫번째 행의 셀 제외한 각각의 셀
```

### 행 병합

*범위가 다를시 병합이 되지 않는다.*

```css
rowspan : 행을 합치는데 사용하고 합치고자 하는 셀의 개수를 속성으로 지정
colspan : 열을 합치는데 사용
```

### 표 제목 삽입

<caption> 사용

### 셀 병합

rwospan : 세로 병합

colspan : 가로 병합
