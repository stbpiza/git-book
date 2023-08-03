## 학습 키워드

- Java ServerSocket
- Blocking vs Non-Blocking

<hr>

## Java ServerSocket
> java.net 패키지의 ServerSocket 클래스를 사용하여 서버를 구현할 수 있다.
- ServerSocket 클래스는 클라이언트의 연결 요청을 기다리는 역할을 한다.
- 클라이언트의 연결 요청이 있을 때까지 accept() 메소드는 블로킹된다.
- 클라이언트의 연결 요청이 있으면 Socket 객체를 생성하여 반환한다.
- Socket 객체는 클라이언트와 통신할 수 있는 스트림을 제공한다.
- ServerSocket 객체를 생성할 때 포트 번호를 지정한다.
- 연결이 종료되면 ServerSocket과 Socket 객체를 닫아야 한다.

```java
public class Server {
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(8080);
        Socket socket = serverSocket.accept();
        InputStream in = socket.getInputStream();
        OutputStream out = socket.getOutputStream();
        ...
        in.close();
        out.close();
        socket.close();
        serverSocket.close();
    }
}
```

## Blocking vs Non-Blocking
> 블로킹과 논블로킹은 입출력 작업의 방식을 말한다.
- 블로킹 방식은 입출력 작업이 완료될 때까지 스레드가 블로킹된다.
- 논블로킹 방식은 입출력 작업이 완료되지 않아도 스레드가 블로킹되지 않는다.
- 블로킹 방식은 입출력 작업이 완료될 때까지 스레드가 블로킹되기 때문에 스레드가 많이 생성되면 컨텍스트 스위칭이 빈번하게 발생하여 성능이 저하된다.
- 논블로킹 방식은 입출력 작업이 완료되지 않아도 스레드가 블로킹되지 않기 때문에 스레드가 많이 생성되어도 컨텍스트 스위칭이 발생하지 않아 성능이 저하되지 않는다.
- 논블로킹 방식은 입출력 작업이 완료되었는지 주기적으로 확인해야 하기 때문에 코드가 복잡해진다.