# Tmoh V16 — actual test results

**Date:** 2026-11-10

## Method

Loaded original HTML and all CSS/JS modules in actual Chromium using Playwright (`page.set_content` + script/style injection). Direct navigation to the local HTTP test server was blocked by the browser environment (`net::ERR_BLOCKED_BY_ADMINISTRATOR`), so browser-origin features were **not** end-to-end tested. Replaced localStorage with an in-memory compatible shim; did not send any private student data to an external service. Created a clearly labeled **demo profile** with sample sessions and tasks for screenshots.

Both runs: desktop viewport **1440×940**, mobile viewport **390×844**, no captured JavaScript page errors or console errors.

## Passed, desktop and mobile

- Loaded all 18 JS modules, including V16, with no script exceptions.
- Six main navigation buttons displayed.
- Homepage rendered 4 stat cards and today's 3 test tasks from the profile, with correct computed study time and points.
- Ticking a task checkbox changed the weekly completion percentage and saved profile state.
- Study home showed only the four subjects in the demo profile.
- Selecting Arabic exposed the six study tools; selecting the available foundational lesson «كان وأخواتها» persisted selection.
- Local source-based summary displayed correct names of cases: **اسم كان مرفوع، خبر كان منصوب**.
- Source-based question displayed, accepted an answer, showed correction, saved a test quiz outcome.
- ChatBook displayed eight learning-mode tiles and prepared a lesson-aware conversation prompt.
- Reward dashboard loaded, original reward tools expanded.
- Journey weekly recap loaded from sample data.
- Other tools showed 8 primary cards; calculator computed `9 × 4 = 36`.
- Calendar created an event and showed it.
- Support note was saved *locally* and verified in `tmoh2` through the shim.
- No horizontal overflow on the home route at both tested viewport sizes.
- Screenshots generated for home, study tools, and ChatBook in both viewports.

## Not tested / not completed

- Real Cloudflare chatbot availability, response accuracy, vision input, or PDF parsing by backend.
- Live GitHub Pages after upload; app files are not yet deployed.
- Actual PWA install/Service Worker caching in an HTTP origin; standalone Android APK or Windows EXE.
- Real persistent browser storage across a browser restart; IndexedDB PDF reading with a real file; optional cloud/Supabase setup.
- Official curriculum coverage: full Ministry textbooks not verified or imported.
- Full French/English/Spanish localization of new screens.
- AI answer quality guarantees; source-excerpt prompts are best-effort, not validation.

## Source integration notes

The existing Cloudflare URL was preserved exactly: `https://tmoh-chatbot-2027.abdelrhmanaboelsod122.workers.dev/`. The project remains local-first with `tmoh2`. Screenshots are **sample/demo data**, not a real student's achievements.

Results are supported by the included `V16_TEST_RESULTS.json` and screenshots from the isolated Chromium run.
