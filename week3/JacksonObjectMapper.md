## 학습 키워드

- Jackson ObjectMapper 란
- ObjectMapper
- `@JsonProperty`

<hr>

## Jackson ObjectMapper 란
- DTO를 JSON으로 변환하거나, JSON을 DTO로 변환해주는 도구이다.
- JSON은 String 형태이므로 DTO의 값들을 하나씩 String으로 만들어서 JSON화 시킬 수도 있지만,
- Jackson ObjectMapper를 사용하면 알아서 만들어 준다.
- 실제로 Spring에서는 아무런 코드를 추가하지 않더라도 요청과 응답을 Jackson ObjectMapper가 변환해준다.
- DTO = JSON 이라는 생각이 들게 만들만큼 자연스럽게 녹아있다.
## ObjectMapper
- ObjectMapper를 직접 사용하면 직렬화 역직렬화가 가능하다.
- 자바 객체를 JSON String이나 바이트 배열로 변환해주고,
- JSON 문자열을 Java 객체로 변환해준다.
- ObjectMapper는 생성시 비용이 많이 들기 때문에 Bean이나 static으로 생성해서 재사용 하도록 권장하고 있다.
## @JsonProperty
- JSON 변환 시 변수명과 JSON name이 다른 경우가 있다.
- 예를 들면 자바의 변수명에는 - 를 사용할 수 없는데 JSON에서는 사용 가능하다.
- 이런 경우 @JsonProperty를 사용해서 이름이 다른 데이터를 매핑시켜줄 수 있다.
- 기본적으로는 setter의 이름으로 JSON name과 매핑하지만,
- @JsonProperty("name") 처럼 작성하면 지정한 이름과 JSON name이 매핑된다.