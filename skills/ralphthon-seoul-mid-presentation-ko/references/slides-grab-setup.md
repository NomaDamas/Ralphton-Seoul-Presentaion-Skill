# slides-grab 설치 가이드 (KO)

`slides-grab`이 없는 경우 이 절차를 안내합니다.

## 공식 npm 설치
```bash
npm install slides-grab
npx playwright install chromium
npx skills add ./node_modules/slides-grab -g -a codex --yes --copy
npx slides-grab --help
```

그 다음 Codex를 재시작해야 slides-grab 스킬이 로드됩니다.

## 메모
- 덱은 `decks/<deck-name>/` 아래에서 작업합니다.
- `slides-grab edit`, `build-viewer`, `validate`, `pdf`, `convert`는 모두 `slide-*.html`이 있는 덱 디렉터리가 필요합니다.
