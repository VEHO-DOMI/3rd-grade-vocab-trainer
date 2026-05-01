# CLAUDE.md — 3rd Grade Vocab Trainer (G3)

Internal docs for Claude Code sessions and future maintainers. For users see [README.md](README.md). For workspace-wide rules see [`../DOMIGO.md`](../DOMIGO.md).

## Architecture

Single-file SPA. G3 was the original "canonical template" for newer trainers; it was the first to ship the campaign mode with chapter-based progression. No build pipeline.

- Total: ~18,537 lines (the largest of the four)
- `const vocabData = {` starts at line **3907**

## File layout

```
3rd-grade-vocab-trainer/
├── index.html         ← entire app (HTML + inline CSS + inline JS + vocabData)
├── avatars/           ← 50 PNG avatars
├── campaign/          ← story-mode assets (chapter scenes, character art)
└── README.md, CLAUDE.md, CHANGELOG.md
```

## Modes shipped

**Practice modes:** Full, Sprint, Speed Round, Multiple Choice, Flashcards.

**Exercise types:** Context (easy/hard), Definition (easy/hard), Translation, Mix.

**Vocab arcade** (curated per-unit, A2):
- Memory Match (10 pairs, phrase support), Word Hunt (A2+ categories), Spelling Bee (7 rounds)
- Group Sort, Matching Pairs, Anagram

**Grammar arcade:** chat-sim campaign renderer, group-sort / matching-pairs / anagram task types. Campaign card has gradient style + progress bar (G3 was the design template for G1/G2).

**Live multiplayer:** Battle Arena, Class Quiz.

## Firebase

- Project: `veho-vocab`
- Realtime DB: `https://veho-vocab-default-rtdb.europe-west1.firebasedatabase.app`
- Firestore path: `classes/<CLASS_ID>/students/<slug>/`
- `let CLASS_ID = null;` — set per class during login.

## Deploy

Push to `main` → GitHub Pages → https://veho-domi.github.io/3rd-grade-vocab-trainer/. No CI, no build step.

## Conventions (the things that have bitten us)

- **Language level A2.** Definitions ~8–14 words, context sentences 8–18 words. Past simple, present simple, present perfect (where taught), simple modals.
- **Definitions must not leak the headword.**
- **Context sentences must be original** — never copy the textbook example.
- **German `g` field is verbatim from MORE! 3.**
- **`cf` field only when needed** (sentence form differs from headword).
- **Vary verb forms** — past, 3rd person, -ing.
- **Single-file edits at scale** — split file into 3 parts, edit chunk, concatenate.
- **Campaign progress isolation** — see fix on 2026-04-06: campaign progress was leaking across accounts on shared devices. Storage is now scoped per-student.
- **Always `git pull` before editing.**

## Vocabulary source

`Domi Gym 2025:26/3A (2025:26)/MORE 3 Materials & Resources/` — full vocab list .docx is in this folder. Extract verbatim, do not hallucinate.

## Known issues / TODOs

- Grammar audit on 2026-04-12 deduped M3 from 969 → 606 items; verify newly added structures don't reintroduce dupes.
- Long-term: fold into unified DomiGo app.
