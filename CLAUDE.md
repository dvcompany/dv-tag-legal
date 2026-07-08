# dv-tag-legal

DV SEO 매니저(Chrome 확장)의 홈페이지 + 개인정보처리방침 정적 사이트.
GitHub Pages 호스팅: https://dvcompany.github.io/dv-tag-legal/

자매 레포: `c:\dev\dvmkt\naver-tag-picker` (확장 본체).

## 파일

- `index.html` - Google OAuth 브랜딩 인증용 홈페이지. **개인정보처리방침 URL과 도메인이 분리되어야 인증 통과**라 별도 페이지로 운영.
- `privacy.html` - 개인정보처리방침. **단일 소스는 `c:\dev\dvmkt\naver-tag-picker\docs\privacy.html`**, 여기로 통째 복사 + commit + push 하는 미러. 직접 편집 금지(편집해도 다음 동기화에서 덮어쓰임).
- `.nojekyll` - **빈 파일, 절대 삭제 금지.** GitHub Pages legacy Jekyll 빌드가 HTML 파일 여러 개 + 한글 콘텐츠 조합에서 "Page build failed"로 실패해 사이트 갱신이 조용히 안 됨(URL은 200이지만 옛 콘텐츠가 캐시됨). `.nojekyll`이 Jekyll을 우회시켜 파일 그대로 서빙.

## 빌드/배포

없음. push 즉시 GitHub Pages가 정적 서빙. 빌드 상태 진단:

```bash
gh api repos/dvcompany/dv-tag-legal/pages/builds/latest
```

`status`(building/built/errored), `error.message`를 확인. 갱신이 안 보이면 브라우저 캐시 의심 + 위 명령으로 빌드 자체 상태부터 본다.

## privacy.html 동기화 절차

1. `naver-tag-picker/docs/privacy.html`을 먼저 편집·확정
2. 동일 내용을 본 레포 `privacy.html`로 통째 복사
3. 두 레포에서 각각 commit + push (확장의 동의 체크박스 링크와 호스팅 페이지 정합성 유지)

## 언어

모든 사용자 응답은 한글로 작성. 코드·명령어·파일 경로·영문 고유명사는 원문 그대로.

## Commit 컨벤션

Conventional Commits + 한글 본문: `feat:` / `fix:` / `chore:` / `docs:`. 본문은 한글 1~3줄, "왜"를 적는다.
