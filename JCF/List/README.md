# List

*인덱스로 관리하며 중복해서 저장이 가능하다.*

List의 단점

*삽입, 삭제가 빈번하게 발생하는 경우 메모리 소모가 심하다.*

List 컬렉션의 특징 및 주요 메소드

- 객체 추가

    boolean add(E e) : 주어진 객체를 맨끝에 추가

    void add(int index E element) : 주어진 인덱스에 객체를 추가

    set(int index, E element) : 주어진 인덱스에 저장된 객체를 주어진 객체로 봐꿈

- 객체 검색

    boolean contains(Object o) : 주어진 객체가 저장되어 있는지 여부

    E get(int index) : 주어진 인덱스에 저장된 객체를 리턴

    isEmpty() : 컬렉션이 비어있는지 조사

    int size() : 저장되어있는 전체 객체수를 리턴

- 객체 삭제

    void clear() : 저장된 모든 객체를 삭제

    E remove(int index) : 주어진 인덱스에 저장된 객체를 삭제

    boolean remove(Object o) : 주어진 객체를 삭제

- ArrayList

    *초기용량은 10이며 초과시 자동으로 늘어나며 값을 고정할수 있다.*

    *객체를 제거할시 바로 뒤 인덱스부터 마지막 인덱스까지 모두 앞으로 1씩 당겨진다*


- Vector

    ```
    ArrayList와 동일한 구조를 가지며 배열의 크기가 늘어나고, 줄어듬에 따라서 자동으로 크기가 조절이 됩니다
    ```

    *Vector는 스레드 동기화를 할수 있다*

    *복수의 스레드가 동시에 Vector에 접근해 객체를 추가, 삭제하더라도 스레드는 안전하다*

    ```java
    // 기본타입의 값을, List 컬렉션으로 관리하고 싶으면,
    // 기본타입에 대응되는 Wrapper Type class를 사용
    List<E> list = new Vector<E>();
    ```

- LinkedList

    *특정 인덱스에서 객체를 제거하거나 추가하게 되면 바로 앞뒤 링크만 변경한다.*

    *빈번한 객체 삭제와 삽입이 일어나는곳에선 ArrayList보다 좋은 성능을 가짐*
