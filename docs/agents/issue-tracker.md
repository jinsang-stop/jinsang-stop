# Issue tracker: GitHub

이 저장소의 이슈와 PRD는 **GitHub 이슈**로 관리한다. 모든 작업에 `gh` CLI를 쓴다.

## 이슈가 사는 곳

| 이슈 | 저장소 | 제목 |
|---|---|---|
| PRD | `jinsang-stop/jinsang-stop` | `[PRD vN] ...` |
| 슬라이스 (공통 계약·데모·AC) | `jinsang-stop/jinsang-stop` | `[Slice] ...` |
| 파트별 작업 | `jinsang-stop-frontend` / `jinsang-stop-backend` / `jinsang-stop-voice` | `[Feat] <번호> <목표>` |

파트별 작업 이슈는 GitHub 하위 이슈(sub-issue)로 슬라이스 이슈에 연결한다.
브랜치(`feat/#N`)와 커밋(`[Feat/#N]`)의 번호는 **파트 저장소 이슈 번호**다.

## 규약

- **이슈 생성**: `gh issue create --title "..." --body "..."`. 여러 줄 본문은 heredoc을 쓴다.
- **이슈 읽기**: `gh issue view <number> --comments`. 라벨도 함께 가져온다.
- **이슈 목록**: `gh issue list --state open --json number,title,body,labels,comments --jq '[.[] | {number, title, body, labels: [.labels[].name], comments: [.comments[].body]}]'` 에 필요한 `--label` / `--state` 필터를 붙인다.
- **댓글**: `gh issue comment <number> --body "..."`
- **라벨 추가/제거**: `gh issue edit <number> --add-label "..."` / `--remove-label "..."`
- **닫기**: `gh issue close <number> --comment "..."`
- **다른 저장소**: `-R jinsang-stop/jinsang-stop-backend`처럼 지정한다.

저장소는 `git remote -v`에서 추론한다 — 클론 안에서 실행하면 `gh`가 자동으로 한다.

## 스킬이 "이슈 트래커에 발행"이라고 하면

GitHub 이슈를 만든다.

## 스킬이 "해당 티켓을 가져와"라고 하면

`gh issue view <number> --comments`를 실행한다.
