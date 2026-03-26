# slides-grab 설치 가이드 (KO)

`slides-grab`이 없는 경우 이 절차를 안내합니다.

## 기본 설치
```bash
git clone https://github.com/vkehfdl1/slides-grab.git && cd slides-grab
npm ci && npx playwright install chromium
npm exec -- slides-grab --help
```

## Codex 스킬 설치
```bash
npm exec -- slides-grab install-codex-skills --force
```

그 다음 Codex를 재시작해야 slides-grab 스킬이 로드됩니다.

## 메모
- 덱은 `decks/<deck-name>/` 아래에서 작업합니다.
- `slides-grab edit`, `build-viewer`, `validate`, `pdf`, `convert`는 모두 `slide-*.html`이 있는 덱 디렉터리가 필요합니다.
