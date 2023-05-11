## 학습 키워드

- Domain Model 이란
- Repository
- VO(Value Object)

<hr>

## Domain Model 이란
- 동작과 데이터를 모두 통합하는 도메인의 개체 모델
- 도메인 모델을 사용하여 해당 도메인과 관련된 문제를 해결할 수 있음
- 다양한 엔티티, 엔티티의 속성, 역할, 관계, 제약을 포함하고, 
- 문제에 대한 솔루션이나 기술적은 부분은 포함하지 않음
- UML에서는 클래스 다이어그램을 사용해서 도메인 모델을 표현 가능하다.
## Repository
- 도메인 모델을 관리한다.
- JPA의 Repository는 Entity 객체를 보관하고 관리하는 역할
- DAO는 데이터베이스, Repository는 도메인 모델에 초점이 맞춰져 있다.
- 크게 보면 유사한 작업을 수행한다.
## VO(Value Object)
- 값을 표현하는 객체
- 불변성
  - setter를 만들지 않아서 수정이 불가능하다.
  - VO에 담긴 값은 항상 원본 값이라고 믿을 수 있다.
- 동등성
  - VO는 객체의 주소로 같은지 비교하지 않는다. (동일성 X)
  - 값 자체가 같으면 같은 객체라고 본다. (동등성 O)
- 엄밀하게 나누면 DTO와 다르지만 혼용해서 쓰는 경우도 있다.