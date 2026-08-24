# Decisions

Format: date · decision · why · revisit when

## 2026-08-24 · Ignore community tier ranking as truth

**Decision:** Use the provided tier-list image as a **discovery source for names only**. Do not treat S+++…F− placement as evaluation signal.

**Why:** Community vibes ≠ controlled native-harness performance. Our publishable claim needs reproducible tasks and metrics.

**Revisit:** Never as ranking evidence; always fine as a candidate-discovery artifact.

## 2026-08-24 · Separate harness vs model vs runtime

**Decision:** Tag each candidate as `harness`, `runtime/gateway`, or `ambiguous`. Evaluate harnesses first; track runtimes (e.g. OpenClaw) as orchestrators.

**Why:** Mixing “which model” with “which loop” and “which multi-agent bus” muddies native harness claims.

**Revisit:** After first pilot if taxonomy fails in practice.

## 2026-08-24 · Continuity lives in project files + later GitHub

**Decision:** Keep `BRIEF` / `STATUS` / `DECISIONS` / `LEARNINGS` / harness list / eval log as the source of continuity; mirror to GitHub once the public repo exists.

**Why:** Research continuity must survive chat resets; public repo is the long-term archive.

**Revisit:** When repo is created — switch “source of truth” note here.

## 2026-08-24 · Personal spend stays out of the public repo

**Decision:** Keep all personal token / billing spend data **out of** the public GitHub tree. Do not commit `TOKEN-SPEND.md`, usage-dashboard screenshots, or usage CSVs. Track spend only in private/local project copies.

**Why:** Public research repo should not expose account billing UI or private usage exports.

**Revisit:** Never for raw spend artifacts.

## 2026-08-24 · Wave 1 is a Grok-model-driven harness comparison

**Decision:** Wave 1 evaluates harness effect. **Grok-native cluster** (Grok held roughly fixed): **Grok Build**, **Pi** (earendil-works / pi.dev; OMP upstream/control), **OMP / Oh My Pi**, **Cursor Grok**, **Hermes Agent** (Nous Research), and **Prime Agent** (try; Grok often needs `XAI_API_KEY`, SuperGrok OAuth may be incomplete). **Matrix expansion** (native routing; not Grok-only): **Amp**, **FX** (Vercel Labs), **Codex CLI** (OpenAI-native baseline). Optional follow-on: OpenCode. Claw-family forks, vibe app builders, and Claude Code are out of scope for this wave.

**Why:** Research question 1 is harness-not-model. Starting with one model family (Grok) isolates orchestration differences on the Grok-capable surfaces. **Pi** is in the SUT set so OMP is not treated as the whole Pi lineage. Hermes is in because its docs report SuperGrok / xAI OAuth. Amp / FX / Codex were added as requested installs to widen the matrix; claiming they are Grok-fixed would confound the original control.

**Revisit:** After Wave 1 protocol exists and first pilots are logged.

## 2026-08-24 · Wave 1 matrix expansion is not a Grok-only claim

**Decision:** Amp (ampcode.com → `amp`), FX (vercel-labs/fx → `fx`), and Codex CLI (OpenAI → `codex`) are Wave 1 SUTs. Log each run with the harness’s actual provider/model. Codex is a **cross-lab baseline**, not a Grok-native SUT. Amp uses its own routing. FX typically uses Vercel / Vercel AI Gateway.

**Why:** Mixing “Grok held fixed” with lab-locked or gateway-routed harnesses without labeling the routing would invalidate the Grok-native contrast. Honest metadata is cheaper than a fake single-model story.

**Revisit:** If Amp or FX later expose a stable Grok route worth a controlled subsample; still keep Codex labeled OpenAI-native.

## 2026-08-24 · Heavy repo work via Cursor cloud agents

**Decision:** All non-trivial development on `bnivanov/llm-harness-eval` is done by **Cursor cloud agents**. Harness Reviewer (Grok Bot) steers, scopes, dispatches, reviews results, and keeps light continuity files — it does not burn Bot quota on heavy coding.

**Why:** Conserve Grok Bot included usage; cloud agents are the stronger coding path for the repo.

**Revisit:** Only if Bobby explicitly wants Bot-side edits for a small continuity tweak.
