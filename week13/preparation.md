## Collection Pattern
> 일관되고 표준화된 방법으로 엔드포인트 설계 및 구현
### 메서드
- GET - 검색, 조회
- POST - 새로운 리소스 등록
- PUT - 리소스를 만들거나 대체
- PATCH - 부분 업데이트
- DELETE - 리소스 제거

### 리소스
- 동사가 아닌 명사
```
/post-content (X)    
/content (O)
```
- table 구조가 아닌 작업 단위
```
/order + /item + /address + ... (X)
/orders (O)
```
- 컬렉션과 단일항목 분리
```
/orders (컬렉션)
/orders/1 (항목)
```
- 일관적인 명명 규칙 사용
- 일반적으로는 복수 명사를 사용
- `컬렉션/항목/컬렉션` 이상으로 복잡하게 하지 않는게 좋다.
```
/customers/1/orders/99/products (x)
/customers/1/orders + /orders/99/products (O)
```