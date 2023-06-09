## Layered Atchitecture
> 비즈니스 로직을 독립적으로 분리해서 계층을 나눈 구조이다.
- 에릭 에반스의 DDD 4계층
    - 사용자 인터페이스 : 사용자에게 정보를 보여주고 명령을 해석하는 계층
    - 응용 계층 : 수행할 작업을 정의만 하고, 작업은 도메인 계층에게 위임하는 계층
    - 도메인 계층 : 업무를 직접 수행하는 핵심 계층, 저장은 인프라스트럭처 계층에 위임
    - 인프라스트럭처 계층 : 메시지 전송, 도메인 영속화 등 기술적 기능을 제공하는 계층
- 계층간 결합은 설계 의존성을 한 방향으로만 두고 느슨하게 결합해야 분리한 이점을 살리면서 연결할 수 있다.