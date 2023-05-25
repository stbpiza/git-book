## 학습 키워드

- Hibernate
- 데이터 모델 / 객체 모델
- entityManager
- 트랜잭션
- JPQL

<hr>

## Hibernate
> JAVA ORM 프레임워크
- JPA의 구현체로 내부적으로 JDBC API를 사용
- 하이버네이트를 사용하면 상속, 다형성, JAVA 컬렉션 프레임워크 등을 포함한 객체지향적 방법으로 persistent 클래스를 개발할 수 있다.
- 인터페이스나 base 클래스를 사용하지 않고도 모든 클래스를 persistent 클래스로 만들 수 있다.
- 특별한 데이터베이스 테이블이나 필드가 필요 없고, 런타임 시점이 아닌 시스템 초기화 시점에 대부분의 SQL을 생성한며, 순수 JDBC에 비해 생산성과 성능이 좋다.
- 확장성이 뛰어나서 어떤 환경에서도 잘 확장시킬 수 있다.
- 사용자가 많아서 어느정도 검증된 프레임워크다.
## 데이터 모델 / 객체 모델
### 데이터 모델
> DB에 Table 단위로 저장되는 모델
- Table PK, FK 등 DB에서 필요한 값들이 들어감
- 관계가 Table 단위로 설정되고, FK로 관계가 설정됨
### 객체 모델
> 비즈니스 로직에서 사용하기 위한 객체 모델
- 비즈니스 로직에 필요한 값들이 들어감
- 의존, 상속 등 프로그래밍 언어로 관계가 설정됨
## entityManager
> Entity를 관리해주는 클래스
- 엔티티매니저 내부에 영속성 컨텍스트(Persistence Context)를 만들어 엔티티를 관리
- 
## 트랜잭션
## JPQL