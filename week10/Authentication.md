## 학습 키워드

- Identifier
- **[PostgreSQL](https://www.postgresql.org/) (MySQL, MariaDB와 두드러지는 차별점)**
- OAuth 2.0
- Bearer Token 옵션
- SecurityFilterChain
- `@Configuration`
- `@EnableWebSecurity`
- Filter vs OncePerRequestFilter
- FilterChain
- SecurityContext

<hr>

## Identifier
> 어떤 대상을 유일하게 식별 및 구별할 수 있는 이름을 뜻한다.
- 사용자의 경우 해당 사용자인지 식별할 수 있는 식별자가 반드시 필요하다.
## PostgreSQL (MySQL, MariaDB와 두드러지는 차별점)
- 오픈소스다.
- 거의 모든 OS에서 사용가능하며, 라즈베리 파이 등 상용 하드웨어에서도 사용가능하다.
- 대량 데이터를 효율적으로 처리할 수 있는 고급 쿼리 최적화 도구가 있다.
- 다중 버전 동시성 제어(MVCC)를 지원한다.
## OAuth 2.0
> OAuth 2.0은 인터넷 사용자들이 비밀번호를 제공하지 않고 다른 웹사이트 상의 자신들의 정보에 대해 웹, 모바일 및 데스크톱 애플리케이션들이 접근할 수 있는 방법을 제공하는 것이다.
- OAuth 2.0은 인증(Authentication)과 권한부여(Authorization)를 위한 표준 프로토콜이다.
- 이미 인증을 거친 서비스에서 제공하는 API를 통해 사용자의 정보를 안전하게 제공받을 수 있다.
- 사용자의 실제 자격 증명 없이도 애플리케이션이 사용자 데이터에 액세스할 수 있는 안전하고 효율적인 방법이다.
## Bearer Token 옵션
> OAuth 2.0 및 기타 인증/권한 부여 프로토콜에서 사용되는 액세스 토큰 유형
- 클라이언트 애플리케이션이 리소스 소유자(사용자)를 대신하여 보호된 리소스에 액세스할 수 있도록 하는 보안 자격 증명 역할을 한다. 
- 인증 서버에서 생성되며 인증에 성공한 후 클라이언트에 부여된다.
- Bearer Token의 'Bearer'이라는 용어는 토큰이 특정 보안 컨텍스트나 사용자 신원과 연결되지 않으며, 토큰을 소유한 사람은 누구나 보호된 리소스에 액세스할 수 있음을 의미 
- 클라이언트를 인증하는 데 필요한 정보를 전달하므로 무단 액세스를 방지하기 위해 안전하게 기밀로 유지해야 한다.
## SecurityFilterChain
## @Configuration
## @EnableWebSecurity
## Filter vs OncePerRequestFilter
## FilterChain
## SecurityContext