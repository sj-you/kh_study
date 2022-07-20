
# Tree

*검색 기능을 강화시킨 컬렉션이다. ( 계층 구조 활용 )*  

- 이진 트리 구조

    부모 노드와 자식 노드로 구성되어 있다. 

  ```
   왼쪽 자식 노드 : 부모보다 적은 값

   오른쪽 자식 노드 : 부모 보다 큰 값
  ```

    위의 구성을 이용하여 정렬

  ```
    올림차순 : [ 왼쪽노드 → 부모노드 → 오른쪽노드]

    내림차순 : [ 오른쪽노드 → 부모노드 → 왼쪽노드 ]
  ```

- TreeSet

    *이진트리를 기반으로 한 Set 컬렉션이며, 왼쪽과 오른쪽 자식 노드를 참조하기 위한 두 개의 변수로 구성되어 있다.*

    주요 메소드

    특정 객체를 찾는 메소드 : *first(), last(), lower(), higher(), …*

    ```java
    score = scores.first();       // 가장 낮은
    score = scores.last();        // 가장 높은
    score = scores.lower(n);      // n보다 작은
    score = scores.higher(n);     // n보다 높은
    score = scores.floor(n);      // n 이거나 바로 아래
    score = scores.ceiling(n);    // n 이거나 바로 위
    score = scores.pollFirst();   // 제일 작은 값을 반환
    ```

    정렬 메소드 : *descendinglterator(), descendingSet()*

    ```java
    TreeSet<Integer> scores = new TreeSet<>();

    // 내림차순으로 정렬후 Set으로 반환
    NavigableSet<Integer> descendingSet = scores.descendingSet();
    // 오름차순 정렬 후 Set으로 반환
    NavigableSet<Integer> ascendingSet = descendingSet.descendingSet();
    ```

    범위 메소드 : *headSet(), tailSet, subSet()*

    ```java
    reeSet<String> treeSet = new TreeSet<>();
    // c~f 사이의 문자열 검색
    NavigableSet<String> rangeSet = treeSet.subSet("cherry", true, "forever", true);

    ```

- TreeMap

    *이진트리 기반이며, 키와 값이 저장된 Map.Enrty를 저장하고 왼쪽과 오른쪽 자식 노드를 참조하기 위한  두 개의 변수로 구성*

    ```java
    // 오름차순
    NavigableMap<Integer, String> descendingMap = scores.descendingMap();
    Set<Map.Entry<Integer, String>> descendingEntrySet = descendingMap.entrySet();

    // 내림착순
    NavigableMap<Integer, String> ascendingMap = descendingMap.descendingMap();
    Set<Map.Entry<Integer, String>> ascendingEntrySet = ascendingMap.entrySet();

    // ~ 범위의 값 (c~f)
    NavigableMap<String, Integer> rangeMap = treeMap.subMap("cherry", true, "forever", true);
    ```
