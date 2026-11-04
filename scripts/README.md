# scripts

일회성 데이터 작업과 평가용 Python 스크립트입니다. 서비스 본체는 `backend/`(Spring Boot)에 있습니다.

| 스크립트 | 주차 | 역할 |
| --- | --- | --- |
| `law_fetch.py` | 6 | 국가법령정보센터에서 공인중개사법·시행령·시행규칙을 수집해 조 단위 JSON으로 저장 |
| `eval/questions.csv` | 7 | RAG 평가셋 (질문, 정답 조 번호, 모범 답) |
| `eval/run_eval.py` | 7 | 검색 API를 호출해 hit@5 계산 |

## 환경

```bash
python3 -m venv .venv
source .venv/bin/activate   # Windows(WSL)도 동일
```
