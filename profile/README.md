# SKKU Crew

SWE3002-42 Team 7 프로젝트 리포지토리 모음.
성균관대 학생 대상 교내 동아리·학회·프로젝트·스터디·공모전 및 대외활동 매칭 플랫폼.

## 리포지토리

- [`skku-crew-frontend`](https://github.com/SKKU-Crew/skku-crew-frontend): Flutter Web 프론트엔드 (`:3000`)
- [`skku-crew-backend`](https://github.com/SKKU-Crew/skku-crew-backend): Spring Boot 3.5.7 백엔드 + 인메모리 seed 데이터 + ChatGPT MCP 연동 (`:8080`)

## 로컬 실행

```powershell
# 1. 백엔드 (JDK 17+)
git clone https://github.com/SKKU-Crew/skku-crew-backend.git
cd skku-crew-backend
.\gradlew.bat bootRun

# 2. 프론트엔드 (Flutter SDK)
git clone https://github.com/SKKU-Crew/skku-crew-frontend.git
cd skku-crew-frontend
flutter pub get
flutter run -d chrome --web-port 3000
```

- Swagger UI: http://localhost:8080/swagger-ui.html (`Authorize`에 `demo-1` 입력)
- 초기 데이터 복원: `POST http://localhost:8080/api/dev/reset`

## MCP ↔ 프론트 경로 약속

ChatGPT MCP 도구에서 웹 링크를 내려줄 때 아래 경로 사용:

- 공고 상세: `/postings/{id}`
- 지원서 작성: `/postings/{id}/apply`
- 내 지원 현황·결과: `/me/applications`
- 조직 페이지: `/orgs/{orgId}`

## 주요 데모 계정

요청 헤더 `Authorization: Bearer demo-{memberId}`

| memberId | 이름 | 유형 | 비고 |
|---|---|---|---|
| `1` | 김민준 | 개인 | 지원자 (공고 101 미지원 상태 시작) |
| `4` | 박지호 | 개인 | 모집자 (공고 101 작성자) |
| `2` | 이서연 | 개인 | 공고 101 지원자, 공고 106 작성자 |
| `6` | 데이터 분석 학회 D:LAB | 단체 | 공고 103 발표 완료, 공고 104 모집 중 |
| `7` | 로봇 학회 R:BOT | 단체 | 공고 105·111 |
| `8` | SKKU Crew 운영자 | 관리자 | 단체 인증·신고 관리 |

## 문서

- API 명세: [`skku-crew-backend/docs/API.md`](https://github.com/SKKU-Crew/skku-crew-backend/blob/main/docs/API.md)
- 프론트 연동 규칙: [`skku-crew-backend/docs/FRONTEND.md`](https://github.com/SKKU-Crew/skku-crew-backend/blob/main/docs/FRONTEND.md)
- MCP 연동 안내: [`skku-crew-backend/docs/MCP.md`](https://github.com/SKKU-Crew/skku-crew-backend/blob/main/docs/MCP.md)
