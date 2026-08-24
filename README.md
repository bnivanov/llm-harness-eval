# LLM Harness Evaluation

Public research project evaluating **native LLM coding harness** performance — the orchestration layer around models (tool use, repo context, shell/edit loops, permissions, memory, subagents), not the models themselves.

**Target repo:** [`bnivanov/llm-harness-eval`](https://github.com/bnivanov/llm-harness-eval) (public) — publish pending auth.  
**Owner:** Bobby Ivanov (`bnivanov`) · Started 2026-08-24

## Goal

Hold models as controlled as practical and measure how much **harness choice** changes task success, cost, latency, and edit quality. Findings are meant to be reproduced, challenged, and extended.

## Scope

**In scope**

- Terminal / CLI coding agents
- IDE-embedded agent modes used as primary coding loops
- Open-source and commercial harnesses with a runnable coding workflow
- Head-to-head comparison under controlled tasks (same prompts, same repos, same success criteria)

**Out of scope (for now)**

- Pure chat UIs with no agent loop
- App builders / vibe-coding product generators (unless later expanded)
- Ranking models in isolation without a harness
- Treating community tier-list vibes as scientific truth (tier image is **name discovery only**)

## Continuity file map

| File | Purpose |
|------|---------|
| [`BRIEF.md`](BRIEF.md) | Why this exists and what “done” means |
| [`STATUS.md`](STATUS.md) | Current phase and next actions |
| [`DECISIONS.md`](DECISIONS.md) | Architecture / methodology choices with rationale |
| [`LEARNINGS.md`](LEARNINGS.md) | Durable insights from research and evals |
| [`possible-harnesses.md`](possible-harnesses.md) | Master candidate list |
| [`evaluation-log.md`](evaluation-log.md) | Running log of what we evaluate and when |
| [`research/`](research/) | Notes and landscape memos |
| [`waves/`](waves/) | Per-wave scope (SUTs, metrics placeholders, protocol checklist) |
| [`assets/`](assets/) | Public screenshots / source images (non-personal) |

## Privacy note — token spend stays private

Personal Cursor / provider **token spend tracking is private and local only**. This public repo deliberately excludes:

- `TOKEN-SPEND.md`
- Usage dashboard screenshots (billing UI)
- Usage CSVs under `research/usage/` or similar

Do not open PRs that add those files; `.gitignore` is set to keep them out if dropped locally.

## How to contribute findings

1. Read `BRIEF.md` and the latest `STATUS.md`.
2. Prefer adding candidates or clarifying taxonomy in `possible-harnesses.md` (kind: harness / runtime-gateway / ambiguous).
3. Record durable methodology choices in `DECISIONS.md` (date · decision · why · revisit when).
4. Capture durable insights in `LEARNINGS.md`.
5. Log concrete eval runs in `evaluation-log.md` using the template there (task id, model/routing, metrics, artifacts, pass/fail/partial).
6. Keep personal billing / spend data out of the public tree.

## Assets

- `assets/tier-list-source.jpg` — community tier-list image used **only** to discover harness names (placements ignored).

## Waves

- [`waves/wave-1-grok-native.md`](waves/wave-1-grok-native.md) — Wave 1: Grok-native cluster (Grok Build, Pi, OMP, Cursor Grok, Hermes, Prime Agent) plus matrix expansion (Amp, FX, Codex CLI). Setup only; no scores yet.

## Research

- `research/llm-coding-harness-landscape-2026-08.md` — mid-2026 landscape notes.

## License / reuse

Findings and notes are intended for open reuse with attribution. Product names and logos remain trademarks of their owners.
