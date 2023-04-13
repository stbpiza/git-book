## 학습 키워드

- TCP/IP 통신
- TCP와 UDP
- Socket과 Socket API 구분
- URI와 URL
- 호스트(host)
    - IP 주소
    - Domain name
    - DNS
- 포트(port)
- path(경로)
- Java text blocks
- Java InputStream과 OutputStream
- Java try-with-resources

<hr>

## TCP/IP 통신

- TCP/IP 통신은 인터넷에서 정보를 주고받는데 쓰이는 규약 중 하나이다.
- 쉽게 생각하면 원하는 목적지까지 데이터를 잘 전송하는 규칙이라고 보면 된다.

## TCP와 UDP

- TCP는 연결이 필요하고, UDP는 연결이 불필요하다.
- TCP는 등기우편, UDP는 일반우편이라고 생각하면 쉽다.
- 목적지에 데이터가 잘 도달했는지 확인하고, 데이터가 손실되었는지 확인하는게 TCP
- 일단 보내고 데이터 손실만 확인해주는게 UDP


- TCP는 정확성이 보장되지만 속도면에서는 느릴 수 밖에 없다. 때문에 느리더라도 정확성이 보장되어야 하는 경우에 사용한다.
- UDP는 정확성이 보장되지 않더라도 속도는 더 빠르다. 일부 데이터가 유실되더라도 큰 지장없는 라이브스트리밍 등에 사용하기 좋다.

## Socket과 Socket API 구분

- Socket은 인터넷 연결의 종착점
- Socket API는 Socket을 통해 어떻게 연결을 할지에 대한 규칙


## URI와 URL

- URI : Uniform Resource Identifier 통합 자원 식별자 / 인터넷에 있는 자원을 식별하는 '식별자'
- URL : Uniform Resource Locator 통합 자원 탐지기 / 인터넷에 있는 자원의 '위치'를 나타냄
- URI는 식별자이며 URL은 식별자 + 위치 정보까지 들어가있다고 생각하면 된다.
- URI가 더 큰 개념이며 URL은 URI 안에 포함된다.
- www.google.com -> URI 
- https://www.google.com -> URI, URL


- 쉽게 말하면 URL은 입력만 하면 바로 원하는 자원에 바로 이동할 수 있는 주소를 말한다.

## 호스트(host)

### IP 주소

- IP주소는 인터넷 상에서 통신하기 위한 주소를 말한다.
- IPv4는 0.0.0.0 부터 255.255.255.255 까지 있다. 일부 주소는 특별주소로 사용된다. (ex 127.0.0.1)
- CIDR를 통해 IPv4를 더 효율적으로 사용할 수 있다.
- IPv6는 IPv4로 주소가 부족해지면서 새롭게 나왔다. 

### Domain name

- 사람이 웹사이트에 접속하기 위해 숫자로 된 IP주소를 외워서 입력하기는 불편하다.
- 사람이 외우기 쉬운 문자로된 주소를 새롭게 만든 것이 Domain name이다.

### DNS

- DNS(Domain Name System)은 Domain name과 ip를 매칭해주기 위한 시스템이다.
- 우리가 Domain name으로 웹사이트에 접속을 시도하면 DNS를 통해 ip 주소로 변환하여 웹사이트에 접속할 수 있게 해준다.

## 포트(port)

- IP 주소가 특정 컴퓨터를 나타내는 주소라면,
- 포트는 컴퓨터로 들어오는 요청을 특정 프로세스로 연결해주는 번호다.
- 0번부터 65536번까지 설정할 수 있으며, 0~1023번 까지는 예약되어있다.
- http는 80, https는 443, ssh는 22 등이다.
- ip주소 뒤에 붙여서 사용한다.

## path(경로)

- path는 연결한 서버 내부 자원의 경로다.
- 포트로 특정 컴퓨터의 특정 프로세스(서버)까지 왔다면 path는 서버 내부에서 특정 자원을 지정하는 경로라고 생각하면 된다.

## Java text blocks

- Java 15에 등장한 String 입력 방법
- 큰 따옴표 3개 """ 로 감싸서 문자를 작성하면 줄 바꿈과 따옴표도 다 적용이 된다.
- html 태그 \<pre>와 유사하다 

## Java InputStream과 OutputStream

- 외부에서 데이터를 읽거나 외부로 데이터를 출력해주는 기능이다. (바이트 기반)
- 파일 데이터, 네트워크 소켓으로 들어온 데이터, 키보드로 입력한 데이터 등에 사용 가능하다.
- 다양한 추상 메소드들이 정의되어 있어서 필요한 메소드를 오버라이딩하여 사용할 수 있다.


## Java try-with-resources

- 기존에 자원 해제를 해줘야하는 기능들의 경우 try-catch-finally를 사용해서 finally에서 꼭 자원 해제를 해줬어야 했다.
- 이런 반복적인 코드를 제거하기 위해 try-with-resources가 등장했다.
- try() 안에서 자원을 생성하면 try를 벗어나면 자동으로 해제가 되고, 기계적으로 반복작성했던 finally를 사용하지 않아도 된다.


- 매번 똑같이 들어가야하는 코드를 추상화 해줘서 코드 양을 줄여준 기능이다.