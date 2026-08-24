# Wave 1 — Grok-native harness evaluation

**Status:** setup (no scored runs)  
**Opened:** 2026-08-24  
**Control:** hold Grok models roughly fixed; vary the harness

## Goal

Measure **harness effect** on Grok-family coding performance. Keep the model family as constant as practical and change the orchestration layer (tool loop, edits, context, auth, permissions). This wave answers: *same Grok, different harness — what changes?*

It is not a general model bake-off and not a ranking of every CLI on the candidate list.

## Systems under test (Wave 1)

| SUT | Surface | Install / entry | Notes |
|-----|---------|-----------------|-------|
| **Grok Build** | xAI native CLI/TUI | `curl -fsSL https://x.ai/cli/install.sh \| bash` → `grok` | Lab-native harness. Sources: [x.ai/cli](https://x.ai/cli), [xai-org/grok-build](https://github.com/xai-org/grok-build). |
| **OMP / Oh My Pi** | Community Pi-lineage CLI | `curl -fsSL https://omp.sh/install \| sh` → `omp` | [omp.sh](https://omp.sh) / [can1357/oh-my-pi](https://github.com/can1357/oh-my-pi). xAI + SuperGrok OAuth documented. |
| **Cursor Grok** | Cursor IDE agent | Cursor IDE, Grok models in agent mode | IDE-embedded coding loop (this surface), not a second CLI install. |
| **Hermes Agent** | Nous Research CLI | `curl -fsSL https://hermes-agent.nousresearch.com/install.sh \| bash` → `hermes` | First-class SUT. Docs report SuperGrok / xAI OAuth (`xai-oauth`). Sources: [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent), [xAI Grok OAuth guide](https://hermes-agent.nousresearch.com/docs/guides/xai-grok-oauth). Install/auth not yet recorded. |
| **Prime Agent** | Prime Intellect CLI | try: `curl -fsSL https://app.primeintellect.ai/prime-agent/install.sh \| sh` → `prime-agent` | Include if Grok routing works. Grok often needs `XAI_API_KEY`; SuperGrok OAuth may be incomplete (community `xai-oauth` work not clearly landed). |

Auth, binary version, and exact Grok model slug are **run metadata**, not results. Record them per session in `evaluation-log.md` once runs start.

## Optional next (not Wave 1 blockers)

These are plausible Grok-capable follow-ons. Do not delay Wave 1 on them:

- **Pi** (upstream / earendil-works) — minimal harness OMP is built on
- **OpenCode** — large OSS terminal agent
- **Amp** — distributed / remote operator

## Out of scope for Wave 1

- Claw-family forks and OpenClaw-style personal runtimes
- Vibe app builders (Lovable, Bolt, v0, and similar generators)
- Cross-lab model comparison (Claude vs Codex vs Grok as the primary axis)

## Metrics (placeholders)

No scores until protocol + tasks exist. Planned columns:

| Metric | Intent |
|--------|--------|
| Task success | pass / fail / partial against a pre-declared criterion |
| Latency | wall time for the run (and, if available, time-to-first-edit) |
| Tokens / cost | only if the harness exposes it; never infer from private billing UIs |
| Edit reliability | whether patches apply, compile, and survive a basic check |
| Human notes | qualitative failure modes (tool-loop stalls, auth, over-edit, refusal) |

Personal token-spend trackers and billing screenshots stay **out of this repo**.

## Tasks

Protocol design is still open. Do **not** treat the following as a benchmark suite — it is a checklist for what the protocol must specify before Wave 1 runs:

- [ ] Task ids and success criteria (what “done” means, including tests or checks)
- [ ] Shared prompt text (same instruction per SUT)
- [ ] Fixture repos / starting commits
- [ ] Allowed tools / network / secrets
- [ ] Time budget and stop conditions
- [ ] How Grok model identity is pinned or recorded when a harness cannot lock it
- [ ] Artifact policy (logs, diffs, traces — no secrets, no billing dumps)

Until those boxes are filled, Wave 1 remains **setup**.
