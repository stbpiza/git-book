## 학습 키워드

- 환경변수(환경변수를 다루는 법)

<hr>

## 환경변수(환경변수를 다루는 법)
- `application.properties` 또는 `application.yml` 파일에서 환경 변수를 정의    

### `application.properties`
```properties
cloudinary.cloud-name=${CLOUDINARY_CLOUD_NAME}
cloudinary.api-key=${CLOUDINARY_API_KEY}
cloudinary.api-secret=${CLOUDINARY_API_SECRET}
```
### `application.yml`
```yaml
cloudinary:
  cloud-name: ${CLOUDINARY_CLOUD_NAME}
  api-key: ${CLOUDINARY_API_KEY}
  api-secret: ${CLOUDINARY_API_SECRET}
```

- 라이브러리에서 요구하는 경로가 있다면 경로를 지켜서 작성
- 본인이 경로를 커스텀해서 작성해도 된다.

### 값 사용하기
```java
@Value("${cloudinary.cloud-name}")
private String cloudName;
```