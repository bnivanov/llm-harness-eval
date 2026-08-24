# Learnings

## 2026-08-24 — Landscape snapshot (pre-eval)

- By mid-2026, serious coding setups often **compose** harnesses (e.g. Claude Code or Codex as engines) rather than pick a single winner.
- “Harness” language is mainstream: control loop, tools, sandbox, MCP, instruction files (`CLAUDE.md` / `AGENTS.md`), subagents.
- Notable brand churn (sources mid-2026): Gemini CLI → Antigravity CLI; Windsurf → Devin Desktop; Continue acquired by Cursor (reported); Amazon Q path toward Kiro.
- OpenClaw is frequently framed as a **gateway/runtime**, not a pure coding harness — keep taxonomy clean in the candidate list.
- Pi is repeatedly cited as a **minimal extensible** harness; Hermes as **learning / memory-oriented**; Amp as **distributed/remote** operator; Claude Code & Codex as leading terminal coding harnesses.

## 2026-08-24 — Wave 1 operating constraints (pre-eval)

- First scored wave is **Grok-native at the core**, with a **matrix expansion**: Amp, FX, Codex CLI. Pointer: [`waves/wave-1-grok-native.md`](waves/wave-1-grok-native.md). Do not treat expansion SUTs as Grok-fixed.
- **Pi** (earendil-works / pi.dev) is a Wave 1 SUT as the **minimal upstream / control** for OMP — not a duplicate of OMP.
- **Hermes Agent** is a Wave 1 SUT (not optional-next): docs report SuperGrok / xAI OAuth. That is not an install or scored-run result.
- **Amp** uses its own model routing; **FX** typically Vercel / AI Gateway; **Codex CLI** is OpenAI-native. Log routing per run.
- **Prime Agent** is worth trying on Grok, but API-key `xai` (`XAI_API_KEY`) is the reliable path today; SuperGrok OAuth looks incomplete relative to Hermes / OMP.
- Personal billing / token-spend artifacts remain local-only; Wave 1 cost metrics, if any, come from harness-reported usage — not private dashboards.

*(Pilot eval learnings go below this line.)*

