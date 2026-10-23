# CLAUDE.md — a module of the Interactive Pathology Teaching Platform

This repository is one module (a single `index.html`): **Genetics and Pediatric Diseases** (module key `genetics`, storage
prefix `gen_`, Chapter 5 on the front page, after Neoplasia). Built 2026-10-23 from scratch, condensed (high-yield) from the
start (HANDBOOK §4.2), with the app code of `neoplasia`. The title never mentions "Condensed" (or similar).

The platform's decisions, the checklist for modules, the deployment steps, the testing workflow and the lessons learned are
in the platform repository: `third-year-med/Interactive-pathology-platform` → `CLAUDE.md` and `docs/HANDBOOK.md`
(rebuilds: `docs/REBUILD.md`).

- The course data in `index.html` is encrypted with this module's OWN content key, which lives only in the user's Code.gs
  (`CONTENT_KEYS.genetics`). Never commit a key or an unencrypted copy of the course.
- The `<script id="platform-nav">` block is maintained in the platform repo (`modules/platform-nav.js`) and written here
  with `tools/module-release.js refresh` — do not edit it by hand.
- Stable IDs: topics t01–t15 (t15 = Integration; no Practical topic), sections sNNMM, questions q001–q326 (q001–q096 review
  book, q097–q189 genetics quiz, q190–q220 MCQ file, q221–q262 case questions, q263–q326 written for the module),
  cases c01–c16. A new build keeps them (`docs/REBUILD.md`).
- Source of truth for conflicting facts: Robbins Basic Pathology 10th ed., Chapter 7 (user, 2026-10-23).
- The Robbins picture-import file (`neo-picture-import`, keys `gen-robbins-01…59`) is delivered to the user directly and is
  never committed (textbook figures).
- Test changes on the real page with the platform repo's e2e test "Genetics and Pediatric Diseases module (genetics)"
  (`GEN_CONTENT_KEY` in the environment) and `node test/module-smoke/smoke.js` before pushing.
