# Status

**Updated:** 2026-08-24

## Phase

`0 — Project bootstrap` complete → **`1 — Wave 1 setup`** (Grok-native harness comparison). Protocol design still open; no scored runs.

## Now

- [x] Create project space (`llm-harness-eval`)
- [x] Continuity files: BRIEF, STATUS, DECISIONS, LEARNINGS, possible-harnesses, evaluation-log
- [x] Ingest tier-list image → `assets/tier-list-source.jpg`
- [x] First-pass harness extraction + broader missing list
- [x] Public GitHub: https://github.com/bnivanov/llm-harness-eval
- [x] Token spend tracker (private/local `TOKEN-SPEND.md` only; weekday snapshots) — **not in this repo**
- [x] Wave 1 SUT shortlist chosen (Grok Build, OMP, Cursor Grok, Prime Agent) — see [`waves/wave-1-grok-native.md`](waves/wave-1-grok-native.md)
- [ ] Install Wave 1 harnesses on the evaluator machine (in progress)
- [ ] Agree evaluation protocol (tasks + metrics)
- [ ] First pilot eval entry in `evaluation-log.md` (Wave 1 log header exists; **no runs yet**)

## Blockers

- Several image logos still unresolved (hexagon cluster, white K, etc.)
- Wave 1 tasks/protocol not yet specified (intentionally TBD — no placeholder benchmark)

## Next up

1. Finish evaluator-machine installs: `grok`, `omp`, Cursor Grok routing, Prime Agent try-path
2. Draft v0 evaluation protocol against the Wave 1 checklist in `waves/wave-1-grok-native.md`
3. Spelling/verification pass on unverified names (Soulforge, Aizen, …)
