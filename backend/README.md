# backend

Spring Boot 애플리케이션이 들어갈 자리입니다. 1주차에 [Spring Initializr](https://start.spring.io)로 직접 생성합니다.

## 생성 설정 (1주차)

| 항목 | 값 |
| --- | --- |
| Project | Gradle (Groovy 또는 Kotlin DSL 중 선택) |
| Language | Java |
| Spring Boot | 최신 안정 버전 (SNAPSHOT·M·RC 제외) |
| Group | 예: `com.betternine` |
| Artifact | `property-chat` |
| Packaging | Jar |
| Java | 21 이상 |
| Dependencies | Spring Web, Validation, Spring Boot Actuator |

Spring AI(OpenAI, Anthropic, Ollama, PGvector)는 2주차에 추가합니다.

생성된 zip의 내용물을 이 `backend/` 폴더 바로 아래에 풀어주세요. (`backend/build.gradle`, `backend/src/...` 형태)
