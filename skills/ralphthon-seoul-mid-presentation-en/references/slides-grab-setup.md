# slides-grab setup (EN)

Use this when `slides-grab` is missing.

## Standard setup
```bash
git clone https://github.com/vkehfdl1/slides-grab.git && cd slides-grab
npm ci && npx playwright install chromium
npm exec -- slides-grab --help
```

## Codex skill install
```bash
npm exec -- slides-grab install-codex-skills --force
```

Then restart Codex so the installed slides-grab skills are loaded.

## Notes
- Keep each deck in `decks/<deck-name>/`.
- `slides-grab edit`, `build-viewer`, `validate`, `pdf`, and `convert` all require an existing deck with `slide-*.html` files.
