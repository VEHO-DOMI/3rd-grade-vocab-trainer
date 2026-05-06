# CHANGELOG — 3rd Grade Vocab Trainer

Reverse-chronological release history. Going forward, update on each substantive change. Earlier history (pre-2026-04-11) lives only in `git log`.

## 2026-05-06 — Activity Game mode
- New sibling app at `activity/` — teacher-orchestrated group game for 3A: **Draw It** ✏️ / **Show It** 🎭 / **Explain It** 💬, plus mix-mode with per-word category cue.
- Setup: ≥2 group names, time-per-round picker (30 / 60 / 90 s), 3/5/8/∞ rounds-per-group, multi-select modes (≥1 required), multi-select 14-unit grid with quick-chips (All / None / U1–4 / U5–7 / U8–11 / U12–14), live "words available" counter, optional time-bonus toggle (+1 if a group clears all words before time).
- Group scoring with two-stage tie-break (correct-total then skip-total) and 🤝 Tie badge.
- 599 MORE 3 vocab entries categorized **from scratch** through an A2 12–13 yo lens — every word reviewed individually with a written justification (327 high-confidence calls, 272 medium-confidence). Distribution: 127 Draw / 199 Show / 273 Explain. Tooling at `TOOLS/activity-audit-g3/` (extract-vocab.js, extract-docx.js, coverage-diff.js, build-activity-words.js); per-word reasoning in `reports/g3-categorizations.csv`; review guide in `TEACHER_REVIEW.md`. The master `Full Vocabulary List MORE 3 Units 1-14.docx` was used for cross-reference (clean — every vocabData entry appears in the master).
- Mobile-friendly: dark theme with G3 orange accent, prevent-pull-to-refresh, audio context unlock, ARIA-live timer.
- Rich SFX: ascending arpeggio for Correct, descending whoosh for Skip, double-tick countdown beep, klaxon time-up buzzer, 5-note bonus fanfare, round-start chime, game-over chord.
- Big 84-px Correct + Skip buttons side-by-side, Undo demoted to its own row to prevent accidental taps.
- Home-screen card "🎯 Activity Game" links to `activity/`. No login / Firebase / XP — pure classroom group game with `localStorage` history (last 20 games).

## 2026-05-01 — Phase 0 polish (cross-grade)
- Fix stray "60" timer always visible at top of practice modes (`speed-timer-wrap` now properly hidden when not in Speed Round).
- Fix XP-for-zero-correct exploit: ending a session with no correct answers now awards 0 XP instead of streak-bonus + perfect-round bonuses.
- Results page: friendly placeholder for sessions with no attempted words instead of blank `RESULTS` box.
- Word Hunt failure UX softened: 2 mistakes allowed per round (was 1), with "1 try left" feedback after the first miss.
- Identical fix-set applied across G1 (already shipped), G2, G3, G4.

## 2026-04-19 — Bugfix sweep
- Fix Spelling Bee auto-click XP exploit
- Fix results-page navigation

## 2026-04-18 — Polish
- Normalize practice-card subtitle to "Choose units and exercise type"
- Accept single-word corrections in error-correction word-selection mode

## 2026-04-14 — Vocab arcade (G3-tuned)
- Replace auto-categorizer vocab games with curated per-unit Memory Match / Word Hunt / Spelling Bee tasks (all 14 units)
- New: Memory Match (10 pairs, phrase support), Word Hunt (A2+ categories), Spelling Bee (7 rounds)
- Unified context/definition types with progressive 2-tier Hint button (XP penalty)

## 2026-04-13 — Grammar arcade additions
- Group Sort, Matching Pairs, Anagram added to grammar arcade
- Chat-sim campaign renderer
- Campaign card uses dynamic level count
- Redesign G3 campaign card to match G1/G2 gradient style with progress bar
- XP burst + combo tier-up animations across vocab modes
- Distractors added to 94 reclassified gap-fill items
- Fix: gap-fill items without distractors fall back to typed input
- Fix: `saveSessionResults` flashcard-status preservation scoping bug

## 2026-04-12 — Flashcards, level badge, mode switch
- Tinder-style flashcard layout (multiple iterations)
- Flashcard tracking + dictionary integration
- Flashcard status persistence across page refreshes
- Matching parser supports dash-separated prompt format
- Grammar audit: dedup G3 M3 (969 → 606 items), sync cumulative blocks
- Mode switch button restored on home screen and added to profile card
- Level badge: bigger + shadow, fix stuck popup

## 2026-04-11 — Audit & cleanup
- Fix today-card width, back buttons, grade-aware unit names
- Remove redundant mode-switch pill from profile card
- Grammar level filter + M1+M2 structures for review mode
- Mode-aware home screen: grammar mode uses fullwidth-card layout
- Class level card: add `loadClassLevel()`, fix Firestore path
- UI fixes: level progression, leaderboards, button layout

## 2026-04-06 — Campaign progress isolation
- Fix: campaign progress leaking across accounts on shared devices

## Earlier
Original campaign mode buildout (story chapters, social-media simulation), Word Partners (collocation MC), Class Quiz, prestige system, journey map. See `git log` for raw history.
