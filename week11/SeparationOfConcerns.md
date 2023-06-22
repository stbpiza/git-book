## 학습 키워드

- IOException
- `FileOutputStream`
- Mockito  `verify`
- @SpyBean 과 @MockBean 차이

<hr>

## IOException
> 입력 또는 출력 작업이 실패하거나 중단될 때 발생하는 checked Exception
- 예기치 않은 파일 종료, 파일을 찾을 수 없음, 파일 권한 문제, 디스크 가득 찼음, 네트워크 오류, 
- 하드웨어 문제 또는 파일 또는 기타 I/O 스트림에서 데이터를 읽거나 쓰는 것과 관련된 기타 문제 등 
- 다양한 이유로 인해 입출력(I/O) 작업이 실패할 수 있다.
- checked Exception 이기 때문에 반드시 예외 처리를 해야 한다. (try catch 또는 throws)
## FileOutputStream
> 바이트 단위로 파일에 데이터를 출력하는 클래스
- 스트림에 바이트를 쓰는 OutputStream 의 하위 클래스
- 텍스트, 이미지, 오디오 등 모든 유형의 데이터를 파일에 쓸 수 있다.
- write() 메서드를 사용하여 파일에 바이트를 쓸 수 있다.
- close() 메서드를 사용하여 스트림을 닫아야 버퍼에 있는 모든 데이터가 파일에 기록된다.
- 스트림을 닫지 않으면 데이터가 손실될 수 있다.
## Mockito verify
> 특정 메서드가 특정 매개변수로 호출되었는지 확인하는 메서드
- `verify(mock).add("example");` : mock 객체의 add() 메서드가 "example" 로 호출되었는지 확인
- `verify(mock, times(5)).add();` : mock 객체의 add() 메서드가 5번 호출되었는지 확인
## @SpyBean 과 @MockBean 차이
### @MockBean
> 클래스나 인터페이스의 모의 객체를 만든다.
- 모의 객체의 메서드 동작을 지정할 수 있다.
- 특정 파라미터를 입력하면 특정 응답을 받도록 Mocking 할 수 있다.
- 테스트 대상이 아닌 객체를 모의 객체로 만들어서 테스트를 더 간단하게 만들 수 있다.
- 모의 객체는 실제 객체의 메서드를 호출할 수 없다.
### @SpyBean
> 특정 메서드만 Mocking 하고, 나머지 메서드는 실제 객체의 메서드를 호출할 수 있다.
- @MockBean과 달리 실제 객체의 메서드를 호출할 수 있다.
- 특정 메서드만 Mocking하고 나머지 메서드는 실제 메서드를 사용하고 싶을 때 사용하면 좋다.