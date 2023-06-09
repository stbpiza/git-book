## 학습 키워드

- Hexagonal Architecture
- POJO
- [조영호님의 “우아한객체지향” 세미나](https://youtu.be/dJ5C4qRqAgA) 를 보고 노트에 정리(무조건 보셔야 합니다)


<hr>

## Hexagonal Architecture
> 애플리케이션의 비즈니스 로직과 규칙을 외부 구성 요소의 구현 세부 사항으로부터 분리하는 아키텍처 패턴
- 비즈니스 로직과 외부 요소를 분리하여, 비즈니스 로직에 집중하는 아키텍처 패턴이다.
- 아키텍처는 도메인, 애플리케이션, 인프라 계층 3가지 주요 구성 요소로 이루어져 있다.
  - 도메인 계층 : 애플리케이션의 비즈니스 로직과 규칙이 포함
  - 애플리케이션 계층 : 도메인 계층을 사용하는 사용 사례, 애플리케이션별 규칙이 포함
  - 인프라 계층 : 데이터베이스, UI 등 외부 요소가 포함
- Hexagonal Architecture의 핵심은 도메인이 인프라와 독립적이어야 한다는 것이다.
  - 도메인 계층은 인프라 계층의 특정 기술이나 아키텍처에 종속되어서는 안된다.
  - 인프라 계층은 도메인 요구사항에 맞게 설계되어야 한다.
- 도메인 레이어를 핵심으로 하고 인프라 레이어를 외부 레이어로 하는 육각형과 비슷하기 때문에 Hexagonal Architecture라고 불린다.
- 장점
  - 비즈니스 로직에 집중하기 좋다.
  - 묘듈화되어 유지 보수에 유리하다.
  - 구성요소들이 독립적이기 때문에 테스트가 용이하다.
  - 한 구성요소의 변경이 다른 구성요소에 영향을 주지 않는다.
  - 인프라 구성 요소의 전환이 쉽다.
## POJO
> Plain Old Java Object : 프레임워크나 라이브러리에 종속되지 않은 자바 객체
- 데이터를 캡슐화하고 해당 데이터에 액세스 할 수 있는 메서드를 제공하는 자바 클래스이다.
- 인터페이스를 구현하거나 클래스를 확장할 필요가 없으며, 다른 라이브러리에 대한 어노테이션이나 종속성이 없다.
- 일반적으로 엔터프라이즈 애플리케이션에서 사용되며, 데이터 객체를 모델링하고 애플리케이션의 여러 계층 간에 데이터를 전송하는 데 사용된다.
- 장점
  - 간단하고 가볍고 이해하기 쉬워 유지 보수가 쉽다.
  - 외부 종속성이 없어 테스트 하기 쉽다.
## 조영호님의 “우아한객체지향” 세미나
- 의존성이란?
  - 변경에 의한 영향을 받을 수 있는 가능성
- 클래스 의존성의 종류
  - 연관관계 : A에서 B로 이동할 수 있다.
  - 의존관계 : 일시적으로 관계를 맺고 헤어지는 관계.
  - 상속관계 : 구현이 바뀌더라도 영향을 받을 수 있다.
  - 실체화괸계 : 인터페이스의 시그니처가 바뀌었을때만 영향을 받는다.
- 패키지 의존성
  - 심플하게 import가 있으면 의존성이 있다는 것
### 의존성 기본 가이드
- 양방향 의존성을 피하라
  - 양방향이 필요한 경우가 있긴하지면 단방향으로 할 수 있으면 단방향으로 하는게 좋다.
- 다중성이 적은 방향을 선택하라
  - 다대일 방향이 좋다
- 의존성이 필요 없다면 제거하라
- 패키지 사이의 의존성 사이클을 제거하라
