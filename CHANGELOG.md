# CHANGELOG — 3rd Grade Vocab Trainer

Reverse-chronological release history. Going forward, update on each substantive change. Earlier history (pre-2026-04-11) lives only in `git log`.

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
