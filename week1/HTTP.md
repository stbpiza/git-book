## 학습 키워드

- HTTP(Hypertext Transfer Protocol)
- HTTP와 HTTPS의 차이(TLS)
- 클라이언트-서버 모델
- stateless와 stateful
- HTTP Cookie와 HTTP Session
- HTTP 메시지 구조
    - HTTP 요청(Reuqest)와 응답(Response)
        - multipart/form-data
    - HTTP 요청 메서드(HTTP request methods)
        - 멱등성
    - HTTP 응답 상태 코드(HTTP response status code)
        - 리다이렉션

<hr>  

## HTTP(Hypertext Transfer Protocol)

- HTTP란 웹에서 통신(데이터 교환)을 하기 위한 규칙이다.
- 데이터는 결국 0101 이진수로 이루어져있고 어떤 형식에 맞게 작성된 데이터 인지 알아야 해석이 가능하다.
- 마찬가지로 통신으로 넘어온 데이터도 제대로 사용하려면 어떤 형식으로 만들어서 보냈는지 알아야 한다.
- 각자의 언어로 대화하면 대화가 통하지 않듯이 통신도 원활한 소통을 위해 언어를 하나로 통일했다고 보면 되겠다.


- HTTP 메시지 구조는 Method, Path, Version, Header, body 로 구성되어있고,
- 요청을 보내면 응답을 보내는 방법으로 통신한다.

## HTTP와 HTTPS의 차이(TLS)

- HTTP는 기본적으로 전송하는 데이터를 암호화 하지 않고 그대로 보낸다.
- 전송한 데이터는 도착지에 도달하기 전까지 여러 라우터들을 지나야 하는데,
- 암호화 되어있지 않다면 중간에서 꺼내볼 수 있게되고, 모두에게 데이터를 공개하는 셈이다.


- HTTPS는 HTTP에 TLS를 얹어서 함께 사용한다고 생각하면 된다.
- TLS(Transport Layer Security)는 암호화 프로토콜로 암호화, 인증, 무결성 3가지를 보장해준다.
  - 암호화 : 데이터 내용을 암호화해서 데이터를 중간에서 꺼내보더라도 어떤 내용인지 알 수 없게 해준다.
  - 인증 : 내가 A 서버에 요청을 보냈을 때, 돌아온 응답이 A 서버가 보내준 응답이 맞다는 사실을 보장해준다.
  - 무결성 : 보낸 데이터가 중간에 변경되지 않고 원본 그대로 전송됐는지 확인해준다.


- HTTPS는 웹보안의 기본으로, 반드시 적용해야 한다. 

## 클라이언트-서버 모델

- 간단하게 생각하면 클라이언트는 요청을 보내고, 서버는 응답을 해준다.
- 클라이언트는 먼저 요청하지 않으면 서버로 부터 아무런 응답을 받을 수 없다.
- 서버는 아무런 요청이 들어오지 않으면 응답을 보낼 수 없다.


- 이러한 모델이 나온 이유는 연결을 최소화 하기 위함이라고 생각한다.
- 인터넷 데이터 전송량은 물리적으로 한계가 정해져 있기 때문에 불필요하게 계속 데이터를 주고 받으면 속도가 느려지고 비효율적이게 된다.

## stateless와 stateful

- HTTP는 기본적으로 stateless 하다.
- 요청과 응답이 끝나면 모든 정보를 기억하지 못한다. 새로 요청을 보내면 인증을 다시 거쳐야 한다.


- 이유는 클라이언트-서버 모델과 유사하게 연결시간을 최소화 하기 위함이라고 생각한다.
- 다음 요청을 위해 계속 정보를 가지고 있다면 너무 비효율적이다.
- 또한 stateful은 서버가 여러개인 경우 인증을 다시 해야하는 문제가 발생한다.
- 처음 인증에 성공하면 accessToken같은 인증 확인증을 가지고 있으면서, 
- 다음 요청때마다 간소화된 인증으로 빠르게 처리하는 방법이 더 효율적이다.

## HTTP Cookie와 HTTP Session

- Session은 인증 정보를 서버가 가지고 있는 방식이고,
- Cookie는 클라이언트가 가지고 있으면서 요청때 매번 서버에 보내주는 방식이다.


- 보안적 관점에서는 Session이 더 안전하다고 볼 수 있으나, 유저가 늘어나면 서버에 부담이 간다는 단점이 있다.
- Cookie는 인증 정보가 탈취될 위험이 있으나, 유저가 아무리 늘어도 서버에 부담이 적다는 장점이 있다.
- 아무래도 Web 환경에서는 Cookie로 서버의 부담을 덜면서 쿠키를 암호화 하는 등 보안도 챙기는 방법이 유리하다고 생각한다.

## HTTP 메시지 구조

### HTTP 요청(Reuqest)와 응답(Response)

- 기본적으로 요청과 응답의 구조는 동일하다. (Start Line, Headers, 빈 줄, Body)
- 여기서 Start Line만 서로 다르다.
- 요청에는 메소드, 경로, HTTP버전이 들어간다면, 응답에는 HTTP 버전과 Status Code가 들어간다.
- Headers에는 여러가지 정보들이 들어가는데 보통 Content-Length나 Content-Type, 인증 헤더 등이 들어간다.
- Content-Type 중 multipart/form-data가 있는데, 여러 메세지들을 하나로 모아서 보내주는 방식이다.
- 기본적으로 Content-Type은 하나의 타입만 명시할 수 있는데, 글도 작성하고 사진도 올리고 여러 타입을 보내고 싶은 경우에 multipart를 사용한다.
- 메세지 구조는 boundary문자열을 사용해서 여러 메세지들을 이어붙인 형태이다.

### HTTP 요청 메서드(HTTP request methods)

- 요청 메소드는 이번 요청으로 어떤 행동을 하고 싶은지를 나타낸다.
- GET이면 조회, POST면 작성, PUT이면 수정, DELETE면 삭제 같은 식이다.


- 멱등성이란 요청을 여러번 보내도 같은 결과가 발생하는 경우를 말한다.
- GET, PUT, DELETE 등이 멱등성을 가진다.
- 멱등성이 왜 필요한가에 대해 생각해 본다면, 수많은 요청이 들어왔을때 멱등성이 잘 지켜진다고 한다면,
- 모든 요청을 매번 직접 처리하지 않고 캐시를 통해 더 빠르게 응답이 가능해지기 때문인 것 같다.

### HTTP 응답 상태 코드(HTTP response status code)

- 상태 코드는 응답 결과를 빠르게 파악할 수 있는 코드라고 생각하면 된다.
- 100번대 부터 500번대 까지 있으며, 100의자리로 큰 카테고리를 빠르게 파악할 수 있다.


