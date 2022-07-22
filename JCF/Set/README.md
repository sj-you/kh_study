

### HashSet

기본문법

```sql
Set<E> set = new HashSet<E>();
```

![캡처](https://user-images.githubusercontent.com/88135939/180383072-00171fd8-e736-4ed2-b47d-397c8b84012d.JPG)


같을시 : *hashCode() 리턴값 → equals() 리턴값 → 동등객체*

다를시 : *hashCode() 리턴값 → 다른객체 ( equals()에서도 다르면 flase )*

```sql
@Override
  public boolean equals(Object obj) {
    if(obj instanceof Member) {
      Member member = (Member)obj; // 강제형변환
      return member.name.equals(name) && (member.age==age); // 이름과 나이가 같을시
    } else {
      return false;
    } // if else
  } // equals

  @Override
  public int hashCode() {				// 두 문자열이 같으면 같은 코드생성
    return name.hashCode() + age;	// 이름과 나이가 같을시
  } // hashCode
```

***위의 Override한 코드를 lombok의 @EqualsAndHashCoded 를 사용하면 작성할 필요 없다.***

Iterator

```java
Iterator<String> iterator = set.iterator();

while(iterator.hasNext()) { // 꺼낼 요소가 있으면 참 없으면 거짓
  String element = iterator.next();
  System.out.println("\t" + element);
}
```
