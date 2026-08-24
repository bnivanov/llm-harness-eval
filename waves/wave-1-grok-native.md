# Wave 1 — Grok-native harness evaluation (plus matrix expansion)

**Status:** setup (no scored runs)  
**Opened:** 2026-08-24  
**Control:** Grok-native cluster — hold Grok models roughly fixed, vary harness. Matrix expansion (Amp, FX, Codex CLI) uses each harness’s **native routing**; do not treat those three as Grok-only.

## Goal

Measure **harness effect**. The original Wave 1 question remains: *same Grok, different harness — what changes?* That applies to the Grok-capable cluster below.

Amp, FX, and Codex CLI were added as SUTs to widen the matrix (install requested 2026-08-24). They are **not** claimed as Grok-locked:

- **Codex CLI** is primarily OpenAI-native
- **Amp** has its own model routing
- **FX** typically authenticates via Vercel / Vercel AI Gateway

Record provider + model slug per run. Do not collapse expansion SUTs into the Grok-fixed contrast.

## Systems under test (Wave 1)

| SUT | Surface | Install / entry | Notes |
|-----|---------|-----------------|-------|
| **Grok Build** | xAI native CLI/TUI | `curl -fsSL https://x.ai/cli/install.sh \| bash` → `grok` | Lab-native harness. Sources: [x.ai/cli](https://x.ai/cli), [xai-org/grok-build](https://github.com/xai-org/grok-build). |
| **Pi** | earendil-works minimal CLI | `curl -fsSL https://pi.dev/install.sh \| sh` → `pi` (alt: `npm i -g --ignore-scripts @earendil-works/pi-coding-agent`) | **OMP upstream / control.** Minimal harness ([pi.dev](https://pi.dev), [earendil-works/pi](https://github.com/earendil-works/pi)). Include so OMP deltas are measured against Pi rather than treated as a single lineage. Install/auth not yet recorded. |
| **OMP / Oh My Pi** | Community Pi-lineage CLI | `curl -fsSL https://omp.sh/install \| sh` → `omp` | [omp.sh](https://omp.sh) / [can1357/oh-my-pi](https://github.com/can1357/oh-my-pi). xAI + SuperGrok OAuth documented. Compare against **Pi** (upstream control), not as a substitute for it. |
| **Cursor Grok** | Cursor IDE agent | Cursor IDE, Grok models in agent mode | IDE-embedded coding loop (this surface), not a second CLI install. |
| **Hermes Agent** | Nous Research CLI | `curl -fsSL https://hermes-agent.nousresearch.com/install.sh \| bash` → `hermes` | First-class SUT. Docs report SuperGrok / xAI OAuth (`xai-oauth`). Sources: [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent), [xAI Grok OAuth guide](https://hermes-agent.nousresearch.com/docs/guides/xai-grok-oauth). Install/auth not yet recorded. |
| **Prime Agent** | Prime Intellect CLI | try: `curl -fsSL https://app.primeintellect.ai/prime-agent/install.sh \| sh` → `prime-agent` | Include if Grok routing works. Grok often needs `XAI_API_KEY`; SuperGrok OAuth may be incomplete (community `xai-oauth` work not clearly landed). |
| **Amp** | ampcode.com CLI | `curl -fsSL https://ampcode.com/install.sh \| bash` → `amp` | **Matrix expansion.** Own model routing (Sourcegraph lineage). [ampcode.com](https://ampcode.com). Not Grok-only. Install/auth not yet recorded. |
| **FX** | Vercel Labs tiny Zig CLI | `curl -fsSL https://fx.sh/setup.sh \| bash` → `fx` | **Matrix expansion.** [vercel-labs/fx](https://github.com/vercel-labs/fx) / [fx.sh](https://fx.sh). Auth typically `fx login` (Vercel) or AI Gateway key (`AI_GATEWAY_API_KEY` / `fx setup`). Not Grok-only. Install/auth not yet recorded. |
| **Codex CLI** | OpenAI terminal harness | `curl -fsSL https://chatgpt.com/codex/install.sh \| sh` → `codex` | **Cross-lab baseline** (OpenAI-native / ChatGPT-plan auth). Useful OpenAI-stack comparator; not a Grok-native SUT. [openai/codex](https://github.com/openai/codex). Install/auth not yet recorded. |

Auth, binary version, and **actual** model/provider routing are **run metadata**, not results. Record them per session in `evaluation-log.md` once runs start. For Grok-native SUTs, pin or note the Grok slug; for Amp / FX / Codex, record native routing honestly.

## Optional next (not Wave 1 blockers)

These are plausible follow-ons. Do not delay Wave 1 on them:

- **OpenCode** — large OSS terminal agent

## Out of scope for Wave 1

- Claw-family forks and OpenClaw-style personal runtimes
- Vibe app builders (Lovable, Bolt, v0, and similar generators)
- **Claude Code** (not added this wave)
- Treating Amp / FX / Codex as Grok-fixed, or treating Wave 1 as a full Claude-vs-Codex-vs-Grok bake-off

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
- [ ] How model identity is pinned or recorded (Grok slug on Grok-native SUTs; native routing on Amp / FX / Codex)
- [ ] Artifact policy (logs, diffs, traces — no secrets, no billing dumps)

Until those boxes are filled, Wave 1 remains **setup**.
