# property-chat

Spring Boot와 Spring AI로 만드는 AI 부동산 상담 챗봇입니다. 공인중개사법 조문 검색(RAG), 중개보수 계산, 국토교통부 실거래가 조회를 지원합니다.

> 진행 중인 프로젝트입니다. 전체 계획은 [docs/plan.md](docs/plan.md), 설계 결정 기록은 [docs/decisions.md](docs/decisions.md)에 있습니다.

## 주요 기능 (예정)

- **LLM 연동**: OpenAI · Anthropic을 공통 인터페이스로 분리하고, 장애 시 서킷브레이커로 자동 폴백
- **Tool use**: 중개보수 상한 계산, 국토교통부 아파트 실거래가 조회
- **RAG**: 공인중개사법·시행령·시행규칙 조문 검색 (pgvector), 근거 조문을 달아 답변
- **Agent**: 조회 → 계산 → 법령 검색을 모델이 스스로 이어서 수행
- **스트리밍**: SSE 채팅 화면
- **운영**: 재시도·폴백·일일 비용 상한, Langfuse 트레이싱, Testcontainers 통합 테스트, Docker 배포

## 기술 스택

| 영역 | 사용 기술 |
| --- | --- |
| Backend | Java 21+, Spring Boot, Spring AI, Gradle |
| DB | PostgreSQL + pgvector, Spring Data JPA, Flyway |
| Test | JUnit 5, Mockito, Testcontainers |
| Ops | Resilience4j, Actuator, Langfuse, Docker Compose, AWS EC2 |
| Scripts | Python (법령 수집·청킹, RAG 평가) |

## 디렉터리 구조

```
backend/        # Spring Boot 애플리케이션
scripts/        # Python 스크립트 (법령 수집, 평가)
  eval/         # RAG 평가셋과 실행 스크립트
docs/           # 계획, 설계 결정 기록
```

## 로컬 설정

```bash
cp .env.example .env   # 값을 채워 넣기 (.env는 커밋되지 않음)
```

> 이 서비스의 답변은 법률 자문이 아닌 참고 정보입니다.
