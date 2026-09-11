# Issue tracker: GitHub

이 저장소의 이슈와 PRD는 **GitHub 이슈**로 관리한다. 단 원격 저장소는 아직 만들지 않았다 — 저장소를 만든 뒤 여기에 `<owner>/<repo>`를 적는다.
모든 작업에 `gh` CLI를 쓴다.

## 규약

- **이슈 생성**: `gh issue create --title "..." --body "..."`. 여러 줄 본문은 heredoc을 쓴다.
- **이슈 읽기**: `gh issue view <number> --comments`. 라벨도 함께 가져온다.
- **이슈 목록**: `gh issue list --state open --json number,title,body,labels,comments --jq '[.[] | {number, title, body, labels: [.labels[].name], comments: [.comments[].body]}]'` 에 필요한 `--label` / `--state` 필터를 붙인다.
- **댓글**: `gh issue comment <number> --body "..."`
- **라벨 추가/제거**: `gh issue edit <number> --add-label "..."` / `--remove-label "..."`
- **닫기**: `gh issue close <number> --comment "..."`

저장소는 `git remote -v`에서 추론한다 — 클론 안에서 실행하면 `gh`가 자동으로 한다.

## 스킬이 "이슈 트래커에 발행"이라고 하면

GitHub 이슈를 만든다.

## 스킬이 "해당 티켓을 가져와"라고 하면

`gh issue view <number> --comments`를 실행한다.
