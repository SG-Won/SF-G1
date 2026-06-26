---
name: integrate
description: 팀원들의 브랜치에 있는 index.html을 읽어 베스트 요소를 하나의 통합 화면으로 새로 작성하고 push한다. 팀 통합(§4, 카드 D)에 사용. git merge가 아니라 '읽고 새로 작성'.
---

# integrate 스킬 / Merge teammates' wireframes into one

여러 팀원이 각자 브랜치에 만든 화면을 **하나의 통합 프로토타입**으로 합친다.
**핵심: git merge를 쓰지 않는다.** 각 브랜치의 `index.html`을 읽고, 베스트 요소를 **새로 작성**한다(충돌 없음).

## 단계 (Steps)
1. `git fetch origin` 을 실행해 최신 브랜치를 받는다.
2. 합칠 팀원 브랜치를 정한다. 사용자가 이름을 주면 그걸 쓰고, 없으면 `git branch -r` 결과를 보여 주고 어떤 브랜치를 합칠지 묻는다.
3. 각 브랜치의 `index.html`을 읽는다. (`git show origin/<브랜치>:index.html`)
4. 각 화면의 **강점**을 한 줄씩 정리한다. (예: "A는 온보딩 폼, B는 결과 목록")
5. **git merge 금지.** 읽은 내용을 바탕으로 베스트 요소를 합친 **하나의 통합 `index.html`**을 아래 디자인 규칙으로 통일해 새로 작성한다.
6. **지금 브랜치(보통 `integration`)**에 커밋·push한다.
7. 무엇을 합쳤고 무엇을 뺐는지 요약한다. (Vercel이 연결돼 있으면 push가 곧 라이브 갱신)

## 공통 디자인 규칙 (Design rules)
- 외부 라이브러리·CDN·웹폰트 **금지**. 시스템 폰트만: `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Apple SD Gothic Neo", "Noto Sans KR", sans-serif`
- 색: 배경 `#f6f7fb`, 카드 `#ffffff`, 강조 `#4f46e5`(남용 금지), 본문 `#1f2433`, 보조 `#6b7280`, 테두리 `#e5e7eb`
- 모서리 12~16px, 부드러운 그림자, 넉넉한 여백, 모바일·데스크톱 **반응형**
- **한국어 UI**, 버튼·입력은 실제로 동작
- **단일 자기완결형 HTML 파일**(CSS·JS 인라인), 외부 의존성 없음
