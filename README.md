# property-chat

공인중개사법 RAG와 중개보수 계산·실거래가 조회 tool을 갖춘 AI 부동산 상담 챗봇입니다.

> 진행 중인 프로젝트입니다. 전체 계획은 [docs/plan.md](docs/plan.md)에 있습니다.

## 주요 기능 (예정)

- **멀티 LLM 공급자**: OpenAI · Anthropic · Gemini · Ollama를 공통 인터페이스로 추상화하고, 장애 시 자동 폴백
- **Tool use**: 중개보수 상한 계산, 국토교통부 아파트 실거래가 조회
- **RAG**: 공인중개사법·시행령·시행규칙 조문 검색, 근거 조문을 달아 답변
- **Agent**: 조회 → 계산 → 법령 검색을 모델이 스스로 이어서 수행
- **스트리밍**: FastAPI SSE + React/TypeScript 채팅 화면
- **운영**: 재시도·폴백·일일 비용 상한, Langfuse 트레이싱, Sentry, Docker 배포

## 기술 스택

| 영역 | 사용 기술 |
| --- | --- |
| Backend | Python 3.12, FastAPI |
| Frontend | Vite, React, TypeScript |
| DB | PostgreSQL + pgvector |
| LLM | OpenAI, Anthropic, Gemini, Ollama |
| Ops | Docker Compose, AWS EC2, Langfuse, Sentry |

## 디렉터리 구조

```
backend/
  app/
    llm/     # LLM 공급자 추상화와 구현체
    tools/   # 중개보수 계산, 실거래가 조회 등 tool
    rag/     # 법령 수집·청킹·임베딩·검색
  tests/
frontend/    # 채팅 화면
docs/        # 계획 및 설계 문서
```

## 로컬 설정

```bash
cp .env.example .env   # 값을 채워 넣기 (.env는 커밋되지 않음)
```

> 이 서비스의 답변은 법률 자문이 아닌 참고 정보입니다.
