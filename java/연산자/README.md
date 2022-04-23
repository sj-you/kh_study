- 논리 연산자
    
    <aside>
    💡 ! (부정) , &(AND), | (OR)
    
    </aside>
    
    <aside>
    💡 And 는 모두가 참이면 참  |  OR은 하나라도 참이면 참 이다.
    
    </aside>
    
- 단항연산
    
    <aside>
    💡 단항 연산시 앞에 부호를 붙이면 int형이 된다
    
    </aside>
    ```
    **short s = 100;
    int result3 = -s;**
    ```
    
- int 와 int를 연산하면 결과값이 int 형으로 나온다
    
    <aside>
    💡 만약 정확한 값을 원할경우 형변환이 필요하다 ex
    
    </aside>
    
    double : 배정도 실수라고 한다 , float : 단정도 실수
    double result6 = (double) v1 / v2;
    
- **정수 리터럴** : 무조건 int 정수로 가정한다
- **실수 리터럴** : 뒤에 f/F가 없는한, double 타입으로 가정한다.;
- 변수의 타입중 그 어떤 기본타입 보다 문자열 타입이 크다
- String 비교하는 방법
    ```
    <aside>
    💡 **System.out.println(기준문자.equals(비교문자));**
    
    </aside>
    ```
- 연산자
    
    <aside>
    💡  **&& (AND)** : 이항연산자로, 2개의 피연산자가 모두 true일 때만 true!
    
    </aside>
    
    <aside>
    💡 **|| (OR)** : 이항연산자로, 2개의 피연산자 중 하나만이라도 true면, true!
    
    </aside>
    
- 삼항 연산자

---

      삼항( 3개의 피연산자를 사용하는 연산자) 연산자 == 조건값

      형식 : (조건식) ? 참일때의 값 : 거짓일때의 값

- **Entry Point** : 실행진입점 (main)
- **Match.random()**

---

      **Match.random()**은 0.0 ≤ Match.random() < 10 이다.
