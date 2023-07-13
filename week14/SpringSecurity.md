## Spring Security

## CORS 
> Cross-Origin Resource Sharing
- 브라우저에서는 보안상의 이유로 다른 출처의 API 사용을 막는다.
- 하지만 다른 출처의 API를 사용해야만 하는 상황이 있는데,
- 이런 경우 사용을 허가한다는 의미로 HTTP 헤더에 내용을 추가할 수 있다.
- 이것을 CORS라고 한다.
- 일반적으로 프론트와 백엔드를 나눠서 작업하다보면 CORS 설정이 필요하게 된다.

### Access-Control-Allow-Origin
- 서버에서 헤더에 Access-Control-Allow-Origin을 추가하여 CORS 설정이 가능하다.
- 모든 출처에 허용할 수도 있고, 원하는 출처에만 허용해줄 수 있다.
- 보통은 백엔드 - 프론트가 출처가 다른 경우 프론트 출처를 등록 해준다.
- 쿠키의 경우 기본적으로는 CORS 설정이 안되지만,
- Access-Control-Allow-Origin을 * 이 아닌 정확한 출처를 적은 경우에
- Access-Control-Allow-Credentials을 사용해서 전달할 수 있다.


## UserDetails
> Spring Security에서 사용자 정보를 담는 인터페이스

### 오버라이드 메서드
- getAuthorities() : 계정이 갖고 있는 권한 목록을 리턴한다.
- getPassword() : 계정의 비밀번호를 리턴한다.
- getUsername() : 계정의 식별자를 리턴한다. (해외에서 Username은 식별자를 의미)
- isAccountNonExpired() : 계정이 만료되지 않았는지 리턴한다. (true: 만료안됨)
- isAccountNonLocked() : 계정이 잠겨있지 않았는지 리턴한다. (true: 잠기지 않음)
- isCredentialsNonExpired() : 계정의 비밀번호가 만료되지 않았는지 리턴한다. (true: 만료안됨)
- isEnabled() : 계정이 활성화(사용가능)인지 리턴한다. (true: 활성화)