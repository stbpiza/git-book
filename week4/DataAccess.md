## 학습 키워드

- DAO(Data Access Object)
- List
- Map

<hr>


## DAO(Data Access Object)
- 말 그대로 데이터베이스에 접근하기 위한 객체로, 데이터베이스 접근 관련 로직을 모아둔 객체이다.
- JPA의 Repository는 Entity 객체를 보관하고 관리하는 역할로,
- 엄밀히 말하면 DAO와 조금 다르지만 크게 보면 유사하다고 볼 수 있다.

## List
- 리스트는 순서가 있는 저장 공간이다.
- Java 에서는 리스트 아래에 LinkedList, Stack, Vector, ArrayList 등 구현 클래스가 있다.
  - LinkedList : 양방향 포인터 구조로 데이터 삽입, 삭제가 자주 있는경우 유용하다. 
  - Stack : 가장 마지막에 넣은 데이터가 가장 먼저 나오는 구조
  - Vector : 동기화가 보장되지만 성능이 좋지 않아 잘 쓰이지 않는다.
  - ArrayList : 단방향 포인터 구조로 데이터 인덱스가 있어 조회 성능이 좋다.
## Map
- 맵은 Key Value 쌍으로 이루어진 데이터의 집합이다.
- Java 에서는 맵 아래에 Hashtable, HashMap, TreeMap 등 구현 클래스가 있다.
  - Hashtable : 동기화가 보장되고, HashMap 보다 느리다. null 불가
  - HashMap : Key 중복이 불가능하고, 순서가 보장되지 않으며, null값이 올 수 있다.
  - TreeMap : 정렬된 순서로 저장해서 조회 성능이 좋다.
