## 학습 키워드

- Multipart FormData
- `@ModelAttribute`

<hr>


## Multipart FormData
> Content-Type 종류 중 하나로 파일 업로드를 위해 사용한다.

### Multipart
> 여러개의 메세지를 하나의 메세지로 묶어서 전송하는 방식
- 여러 MIME 타입도 하나의 메세지로 묶어서 전송할 수 있다.
- 여러 파일들과 문자 등을 함께 전송할 수 있다.

### multipart/form-Data
- 모든 문자를 인코딩 하지 않았다는 의미
- form 으로 파일 업로드를 위해 사용한다.

```
POST /file HTTP/1.1
Content-Type: multipart/form-data; boundary=-----abcde
Content-Length: 123

-----abcde
Content-Disposition: form-data; name="file"; filename="file.txt"
Content-Type: text/plain

Hello, World!
-----abcde--

```

## @ModelAttribute
> 요청 파라미터를 객체에 바인딩할 때 사용한다.
- 