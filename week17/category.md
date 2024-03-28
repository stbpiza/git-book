## 카테고리 관리 


## Soft Delete
- 데이터를 실제로 삭제하지 않고 삭제 표시를 하여 데이터를 보관하는 방법
- 데이터를 복구할 수 있음
- 데이터가 남아있어서 로그 분석이나 통계를 내기 좋음
- 삭제 표시된 데이터를 구분해야 하므로 성능이 떨어짐
- 유저에게는 삭제된 것처럼 보이면서 관리자 페이지에서는 삭제되지 않은 것처럼 보이게 할 수 있음
- 실제 운영중인 서비스에서는 Soft Delete를 사용하는 것이 좋음
- 민감한 정보는 Soft Delete 뿐만 아니라 데이터 덮어쓰기 등을 활용해 삭제하는 것이 좋음 