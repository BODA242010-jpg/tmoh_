# Tmoh V16 — student-first six-section redesign

This is the **complete frontend source** of the current Tmoh project, extended from V15. It is not a new, empty site. It preserves the existing local-first `tmoh2` profile store, six-grade schoolbooks shelf, old study functionality, login/cloud animation, PWA, and current Cloudflare chatbot URL.

## New student journey (V16)

1. **الرئيسية**: personalized name and dream, actual task completion rate, study hours, open tasks, points, today's checkable tasks, 7-day chart, mood, last session, latest activity, level and rewards shortcuts.
2. **المذاكرة**: only enrolled subjects; choose one subject and lesson, then six tools: timer, summary (text/audio/visual concept map), verified local explanation, scored foundational lesson questions, lesson-specific mistakes, and backlog. All selection persists with the profile.
3. **ChatBook**: eight cards in the reference style, opening the existing text chatbot or preparing a source-aware prompt. `#/assistant` redirects to the same ChatBook interface. This update **does not replace or fix the Cloudflare backend**.
4. **التحفيز والمكافآت**: clean XP/level/badges dashboard, existing reward system within collapsible details.
5. **رحلتي وتقدمي**: study/mood/weekly task figures, weekly recap based on actual records, dream goals and original journey page within details.
6. **أدوات أخرى**: working 2-number calculator, old notes and personal library, local events/calendar, small explicitly limited offline dictionary, profile settings, locally saved support suggestions, and a collapsed list of the other old functions.

## Important limitations

- **The official 2026–2027 curriculum has not all been uploaded.** The existing 78 in-site lessons are original foundational material for secondary grades, not verified official full textbooks. Preparatory grades have no equivalent in-site lesson bank yet. The existing books shelf supports students adding PDFs/official links themselves; adding PDFs locally does not make the chatbot read them.
- **ChatBook is still text-only** on the currently deployed external Worker. Camera image understanding and automated PDF understanding require a separate vision/document backend and explicit opt-in; the new UI does **not** pretend to support them. The PDF card links to the existing book upload/reading area.
- AI explanations can be wrong. Source-related buttons put a grounded excerpt and a warning in the prompt, but that alone does not guarantee accuracy. Do not treat any answer as certified by the Ministry.
- Audio uses optional browser speech synthesis; voice quality varies by OS.
- New interface text is mostly Arabic. The older language selector and partial translations remain; full translation of every new view is not delivered.
- New support suggestions are stored locally **only**, not sent to a real support inbox.
- APK/EXE binaries are not included. The existing PWA assets are retained.

## How to publish

1. Back up your site files and export any important student profiles from Tmoh **before uploading**. Keep copies of PDFs saved to the browser/IndexedDB.
2. Open https://github.com/BODA242010-jpg/tmoh9 and upload **all files from this archive to the repository root** (replace same-name files; do not upload the ZIP as a single website file).
3. GitHub Pages should serve the updated root. Wait for deployment and force refresh the page (`Ctrl+Shift+R` on Windows) without clearing site data. Revisit the PWA after the new service worker has installed.
4. Check `#/home`, `#/studyhub`, `#/chatbook`, `#/rewards`, `#/journey`, and `#/utilities` with both an old account and a new account.
5. Export/import a backup and verify personal documents, exams, sessions and V16 calendar fields.

> This ZIP was **not published directly to GitHub**; the GitHub connector rejected write access (HTTP 403).

## Key source files

- `tmoh-v16.js` — new views, data-driven summaries, linked study tools, navigation and local utilities.
- `tmoh-v16.css` — dark responsive design.
- `index.html` — adds V16 CSS/JS references.
- `app.js` — small validated backup import extension for V16 optional fields; existing ChatBook API URL unchanged.
- `sw.js` — cache version and V16 resource list.
- All previous project files retained.

See `TEST_REPORT_V16.md`, `CURRICULUM_STATUS_V16.md`, and `CHANGELOG_V16.md`.
