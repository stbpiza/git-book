## 학습 키워드

- URI & URL & URN
- MIME type

<hr>

## URI & URL & URN

- 웹에서 URN은 사실상 거의 사용하지 않음
- URI, URL은 거의 비슷한 의미로 많이 쓰인다.

### URI
- Uniform Resource Identifier 통합 자원 식별자 
- 인터넷에 있는 자원을 식별하는 '식별자'
- URL, URN을 포함한 상위 개념

### URL
- Uniform Resource Locator 통합 자원 탐지기 
- 인터넷에 있는 자원의 '위치'를 나타냄
- 위치를 나타내기 때문에 URL을 통해 해당 자원으로 바로 이동이 가능하다.
- 다만 위치가 변경되는 부분에는 취약하다. (404)

### URN
- Uniform Resource Name 통합 자원 이름
- 인터넷에 있는 자원의 '이름'을 나타냄
- 이름을 통해 자원의 위치를 알 수 있는 용도로 사용 가능하다.
- 웹에서는 거의 사용하지 않는다.

## MIME type

- Content 종류를 나타내고, Content-Type 헤더에 전달한다.
- text/plain - 형식이 없는 단순 문자열로 이메일에서 자주 사용
- text/html - html 문서
- text/css - css 파일
- text/javascript - 자바스크립트 파일
- application/xml - xml 형식으로 많이 쓰임
- application/json - json 형식으로 많이 쓰임 (가장 많이 본 형태)

