# ⚾ 홈런볼 (Homerunball)

야구 경기 일정 확인부터 좌석 예매, 팀 순위까지 제공하는 야구 경기 예매 웹 서비스입니다.
KH정보교육원 교육과정에서 5인 팀으로 진행했습니다.

- 개발 기간: 2023.08 ~ 2023.10
- 인원: 5명

## ⚙️ 개발 환경

| 구분 | 내용 |
|---|---|
| Language | Java 17, JavaScript, HTML/CSS |
| Framework | Spring Boot 2.7, Spring JDBC (JdbcTemplate) |
| View | JSP, JSTL |
| DB | Oracle |
| Etc | Spring Mail, Interceptor(회원·관리자 권한), Lombok, Maven |

## 🧑‍💻 내가 맡은 부분 (조준희)

- **경기 관리 (관리자)**: 경기 등록 · 일정 변경 · 결과(점수) 입력 · 목록 · 상세 · 삭제
  - 현재 시각 이전으로는 경기를 등록할 수 없도록 검증
- **경기 결과 → 팀 순위 자동 반영**: 결과 입력 시 팀별 승 · 패 · 무, 승률, 게임차를 SQL로 갱신하고 순위 페이지로 출력
- **팀 관리 (관리자)**: 팀 등록 · 수정 · 삭제, 팀 이미지 연결
- **예매 내역 조회**, 좌석 구역 등록
- 프로젝트 초기 DAO · DTO · RowMapper 구조 생성, GitHub 저장소 관리

## 📁 구조

```
baseball/src/main/java/com/kh/baseball
├── controller   # 화면 요청 처리 (팀, 경기, 예매, 회원, 관리자)
├── rest         # 비동기 요청용 REST 컨트롤러
├── dao          # JdbcTemplate 기반 데이터 접근
├── mapper       # RowMapper
├── dto / vo
├── interceptor  # 회원 · 관리자 권한 체크
└── configuration
```
