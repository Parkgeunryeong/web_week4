# 발표자료 (Reveal.js + GitHub Pages)

Reveal.js를 CDN으로 불러오는 순수 정적 사이트입니다. 별도 빌드 없이 `index.html`만 열면 바로 동작하고, GitHub Pages에 그대로 올리면 배포됩니다.

## 로컬에서 미리보기

`file://`로 그냥 열어도 대부분 동작하지만, 브라우저 보안 정책 때문에 일부 기능(마크다운 플러그인 등)이 막힐 수 있습니다. 로컬 서버로 여는 걸 권장합니다.

```powershell
# Python이 있다면
python -m http.server 8000
```

브라우저에서 `http://localhost:8000` 접속.

## 슬라이드 작성법

- `index.html`의 `<div class="slides">` 안에 `<section>` 하나가 슬라이드 한 장입니다.
- `<section>` 안에 `<section>`을 중첩하면 세로(아래 방향) 슬라이드가 됩니다.
- `class="fragment"`를 붙이면 클릭할 때마다 하나씩 나타납니다.
- `<aside class="notes">`는 발표자 노트 — 발표 중 `S` 키로 스피커 뷰를 열면 보입니다.
- 코드 블록은 `<pre><code class="language-xxx" data-trim data-line-numbers>` 형태로 작성하면 하이라이팅됩니다.
- 커스텀 스타일은 `css/custom.css`에 추가하세요.

## GitHub Pages 배포

1. 이 폴더를 git 저장소로 초기화하고 GitHub에 새 저장소를 만듭니다.

   ```powershell
   git init
   git add .
   git commit -m "Initial slides"
   git branch -M main
   git remote add origin https://github.com/<사용자명>/<저장소명>.git
   git push -u origin main
   ```

2. GitHub 저장소 페이지에서 **Settings → Pages**로 이동합니다.
3. **Source**를 `Deploy from a branch`로 설정하고, 브랜치는 `main`, 폴더는 `/ (root)`를 선택 후 Save.
4. 몇 분 후 `https://<사용자명>.github.io/<저장소명>/`에서 발표자료가 열립니다.

### 발표 중 유용한 단축키

- `F`: 전체화면
- `S`: 발표자 노트 뷰 (별도 창)
- `O` 또는 `ESC`: 슬라이드 전체 개요 보기
- `←/→/↑/↓`: 슬라이드 이동
- URL에 `?print-pdf`를 붙이고 브라우저 인쇄(PDF로 저장)하면 PDF 내보내기 가능

## 테마 바꾸기

`index.html`의 `theme-link` 태그에서 `black.css` 부분을 아래 중 하나로 바꾸면 됩니다:
`white`, `league`, `sky`, `beige`, `simple`, `serif`, `night`, `moon`, `solarized`
