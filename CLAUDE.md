# dv-tag-legal (운영 종료 — 작업하지 말 것)

**이 저장소는 2026-07-15에 운영을 끝냈습니다. 여기에 방침을 다시 올리거나 되살리지 마세요.**

## 무슨 일이 있었나

원래 GitHub Pages로 홈페이지(`index.html`)와 개인정보처리방침(`privacy.html`) 두 장을
서빙했다. Google OAuth 브랜딩 인증에 홈페이지 URL과 방침 URL이 서로 달라야 해서 만든
우회책이었다.

2026-07-15에 정리됐다:

- Google OAuth 브랜딩을 `https://dview.me` + `https://dview.me/privacy`로 변경
- 방침을 디뷰 한 곳으로 일원화 (확장 레포의 `docs/privacy.html`·`docs/privacy.md`도 삭제)
- 확장은 0.2.31(2026-07-10)부터 이미 `dview.me/privacy`를 가리키고 있었다. 그 전엔
  `kimddaehyun.github.io` — 계정 이전 후 404. 이 저장소 주소인 `dvcompany.github.io`는
  확장이 **한 번도** 가리킨 적이 없다(만들어만 놓고 아무도 연결하지 않았다).

→ 가리키는 곳이 하나도 없어 `index.html`·`privacy.html`을 삭제했다.

## 지금 방침은 어디에 있나

**`https://dview.me/privacy`가 단일 소스.** 실체는 Supabase `dview.legal_documents`
테이블의 `body_html`(slug=`privacy`)이고, 디뷰 관리자 화면 `/admin/legal`(Tiptap)에서
편집한다. 확장 관련 고지는 그 문서의 9장. 자세한 건
`c:\dev\dvmkt\naver-tag-picker\CLAUDE.md`의 개인정보처리방침 항목 참조.

## 남은 파일

- `.nojekyll` - 빈 파일. HTML이 없으니 이제 무의미하지만 굳이 지울 이유도 없어 둔다.
- `README.md` / `CLAUDE.md` - 이 안내.

지난 내용은 이력에 있다: `git show HEAD~1:privacy.html`, `git show HEAD~1:index.html`.
