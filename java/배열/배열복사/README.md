 ## 배열의 복사 방법
    
- 배열의 복사방법 1
    
    반복문(for)을 활용한다
    
    ```java
     // 기존 배열의 원소를 새로운 배열에 복사
    		for(int i = 0; i < oldIntArray.length; i++) {
    			newIntArray[i] = oldIntArray[i];
    		}
    ```
    
- 배열의 복사방법 2
    
    offset  :  시작위치
    
    복사를 하고 남은 공간은 null 이 들어간다.
    
    ```java
    System.arraycopy(oldArr, offset, newArr, offset, length);
    ```
    
- 배열의 복사방법 3
    
    length 를 지정할시 기존 배열을 복사하고 지정한 만큼 생성한다.
    ```java
    String[] newArr = Arrays.copyOf(oldArr, length);
    ```
