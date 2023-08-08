## 로그인, 로그아웃 

## 관리자 권한 설정
```java
@Target({ElementType.METHOD, ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Secured({"ROLE_ADMIN"})
public @interface AdminRequired {
}
```

`@Target({ElementType.METHOD, ElementType.TYPE})`
- 어노테이션을 어디에 적용할 수 있는지 지정한다.
- `ElementType.METHOD`: 메소드 선언에만 적용할 수 있다.
- `ElementType.TYPE`: 클래스 선언에만 적용할 수 있다.

`@Retention(RetentionPolicy.RUNTIME)`
- 어노테이션 정보를 언제까지 유지할 것인지 지정한다.
- `RetentionPolicy.RUNTIME`: 런타임까지 어노테이션 정보를 유지한다.

`@Secured({"ROLE_ADMIN"})`
- 유저 ROLE이 ADMIN인 경우에만 실행할 수 있도록 지정한다.
