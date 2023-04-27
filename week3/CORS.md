## 학습 키워드

- CORS 란
    - 동일 출처 정책
    - JSONP
    - `Access-Control-Allow-Origin`
- `@CrossOrigin`

<hr>

## CORS 란
- Cross-Origin Resource Sharing
- 브라우저에서는 보안상의 이유로 다른 출처의 API 사용을 막는다.
- 하지만 다른 출처의 API를 사용해야만 하는 상황이 있는데,
- 이런 경우 사용을 허가한다는 의미로 HTTP 헤더에 내용을 추가할 수 있다.
- 이것을 CORS라고 한다.
- 일반적으로 프론트와 백엔드를 나눠서 작업하다보면 CORS 설정이 필요하게 된다.

### 동일 출처 정책
- 동일 출처 정책은 보안을 위해 만들어진 정책이다.
- 어떤 출처에서 불러온 문서나 스크립트가 다른 출처에서 가져온 리소스와 상호작용하는 것을 제한한다.
- 두 URL의 프로토콜, 호스트, 포트가 모두 같아야 동일한 출처이다.
- 교차 출처 쓰기, 삽입은 보통 허용하고, 교차 출처 읽기는 보통 불허한다.

### JSONP
- script 태그는 동일 출처 정책을 따지지 않는 점을 이용해서,
- 서버에서 JSON이 아닌 자바스크립트 코드를 전달하는 방식이다.
- script로 콜백 함수를 호출하고 response를 받아서 데이터를 처리하는 방식으로,
- 비효율적이기 때문에 사용을 권장하지 않는다.

### Access-Control-Allow-Origin
- 서버에서 헤더에 Access-Control-Allow-Origin을 추가하여 CORS 설정이 가능하다.
- 모든 곳에 허용할 수 있고, 원하는 출처에만 허용해줄 수 있다.
- 보통은 백엔드 - 프론트 연결로 같은 서비스이지만 출처가 다른 경우 등록을 해준다.
- 쿠키의 경우 기본적으로는 CORS 설정이 안되지만,
- Access-Control-Allow-Origin을 * 이 아닌 정확한 출처를 적은 경우에
- Access-Control-Allow-Credentials을 사용해서 전달할 수 있다.
 
## @CrossOrigin
- 클래스나 메소드에 사용 가능한 어노테이션으로,
- Access-Control-Allow-Origin 헤더를 간단하게 추가할 수 있다.
- 원하는 주소를 직접 추가할 수 있고, 아무 주소를 입력 안하면 *로 적용된다.