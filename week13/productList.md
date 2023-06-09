## N+1 문제
> 연관관계가 설정된 엔티티를 조회할 때, 조회된 엔티티의 개수(N)만큼 연관된 엔티티를 조회하기 위해 추가적인 쿼리가 발생하는 문제
### 해결법
1. @ManyToOne을 사용해 Fetch Join or BatchSize를 사용해 IN 쿼리로 조회
   - DDD나 Aggregate 같은 개념에서 벗어나 간단하게 해결하는 방법
   - 그동안 개발하면서 이 방법을 많이 사용했었다.
2. SQL을 직접 또는 간접적으로 써서 Command가 아닌 Query의 효율을 높임
   - 조회만 하는 부분은 Dto fetcher를 사용하기도 함
   - 더 발전하면 CQRS 등으로 이어짐