# hyana's homepage

A personal site styled like a 2000s Korean mini homepage, served by GitHub Pages at https://hyana.github.io/.

## How it is built

- One static file, `index.html`, with no build step and no framework. Keep it that way.
- All content lives in the JSON block `<script id="data" type="application/json">`. Change content there, not in the rendering code.
- Korean text lives under `ko` in that same JSON (`ko.profile`, `ko.chapters`, `ko.entries`, `ko.hackathons`, `ko.posts`, `ko.changelog`). UI strings are in the `KO` map in the script.
- The profile picture is `avatar.gif`, a hand-drawn pixel portrait. The small sprite next to the name and in the mini-room is the `ME` pixel map in the script.
- Album items come from `entries` plus `hackathons`. Tags are derived from each entry's `stack` through `tagName()` and `TAG_ALIAS`.

## Preview

```bash
python3 -m http.server 8000
```

Open http://localhost:8000. Before every commit, click through all five tabs, the Album pages and filters, a few popups, the clickable mini-room objects, and the EN/한국어 toggle. Check at phone width (375px) too, with no sideways scrolling.

## Content rules

- Wording about the owner's work comes from the owner. Ask before adding, cutting or rewording anything about it.
- Never add internal metrics, internal links, codenames, customer names, a phone number or a home address.
- Do not show the owner's Korean name. The Korean pronunciation (햐나) is fine.
- The email address is stored split into `user` and `domain` so it is not one plain string in the source. Keep it that way.
- Every new piece of content needs a Korean version under `ko`. Say which translations need the owner's review.

## Style rules

- No emoji in the UI. Use the pixel icons in `ICONS` or the text symbols in `GLYPH` instead.
- Dates in English use US style: `Oct 2026 – Nov 2026` (en dash), `Nov 16, 2026`, `Present`. Korean uses `2026.10 ~ 2026.11` and `현재`.
- Tags are lowercase, hyphenated and technical (`#react`, `#a11y`, `#incident-response`). Add new ones to `TAG_ALIAS` when the raw stack name is not.
- Fonts: Galmuri11 for labels, numbers and titles, and Gowun Dodum for body text. Gowun Dodum has one weight, so do not rely on bold with it.
- Keep text contrast at 4.5:1 or higher, keep the keyboard focus outline visible, and give images alt text in both languages.
- Pixel art (room, sprite, icons) is drawn from shapes or pixel maps in the script. No AI-generated or traced images.

## Git and publishing

- `public-draft.json`, `photo.webp`, `pixel-options/`, `font-preview.html` and `.claude/` are ignored on purpose. Never commit them.
- Commit with the GitHub noreply address, not a work email: `git config user.email "51047617+hyana@users.noreply.github.com"`.
- Pushing to `main` publishes the site within a minute or two. Never push without the owner's OK.

## Open to-dos

1. More personalization: hobbies, college and a warmer profile intro. Wait for the owner's notes.
2. Decide what the Board is for. It currently holds only links. A Giscus guestbook is the leading idea.
