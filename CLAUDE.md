# 진상 멈춰 (calmdesk)

제품명은 「진상 멈춰」. 코드 식별자는 `calmdesk`를 쓴다.
악성 민원 응대를 음성으로 반복 연습하는 훈련 서비스. 10주 수업 프로젝트, 2인.
MVP 범위는 알바(매장 응대) 한 직업군이다.

스택: React + TypeScript / Java Spring / MySQL / 파이썬 `음성 서비스`(faster-whisper + MeloTTS) / 로컬 `추론 서비스`(llama.cpp)

현재 PRD는 `docs/PRD-v2.md`다. `docs/PRD.md`(v1)는 이력으로만 두고 구현 근거로 쓰지 않는다.

## 저장소 구성

GitHub 조직 `jinsang-stop` 아래 넷으로 나눈다.

| 저장소 | 담는 것 |
|---|---|
| `jinsang-stop/calmdesk` (이 저장소) | 용어집·ADR·PRD, PRD 이슈와 `[Slice]` 이슈 |
| `jinsang-stop/calmdesk-frontend` | React + TypeScript |
| `jinsang-stop/calmdesk-backend` | Java Spring + MySQL |
| `jinsang-stop/calmdesk-voice` | 파이썬 `음성 서비스`, `추론 서비스` 실행 설정 |

코드 저장소의 커밋·브랜치·이슈·PR 규약은 각 저장소의 `CONTRIBUTING.md`와 `.github/`에 있다.

## Agent skills

### Domain docs
도메인 용어집은 `CONTEXT.md`, 확정된 결정은 `docs/adr/`. `docs/agents/domain.md` 참고.

### Issue tracker
이슈와 PRD는 GitHub 이슈로 관리한다. `docs/agents/issue-tracker.md` 참고.

### Triage labels
표준 트리아지 역할 5종의 라벨 매핑은 `docs/agents/triage-labels.md` 참고.
