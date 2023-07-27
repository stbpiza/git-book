## 결제 정보 확인

## PortOne
> 여러 PG사를 한번에 연동하여 사용할 수 있는 결제 서비스
- 과거 이름은 아임포트
- 가볍게 무료로 시작할 수 있고, 결제 테스트는 바로 사용이 가능

## 결제정보 사후 검증
https://developers.portone.io/docs/ko/auth/guide/5/post
1. Access Token 얻기
2. 결제 정보 얻기
3. 금액 비교

## @JsonProperty
> JSON으로 변환할 때, 해당 필드의 이름을 변경할 수 있다.
```java
@JsonProperty("imp_key")
private int impKey;
```
- 외부 서비스와 연동할 때, 외부 서비스의 필드명과 도메인의 필드명이 다를 수 있다.
- 이럴 때, @JsonProperty를 사용하면 외부 서비스의 필드명을 도메인의 필드명으로 매핑할 수 있다.
- 외부 서비스에는 언더바를 사용해서 변수명을 지었으나, 
- 우리 도메인에는 카멜케이스를 사용하기 때문에 매핑 작업이 필요하다.