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

## 2026-08-24 · Personal token spend stays out of the public repo

**Decision:** Keep all personal token / billing spend data **out of** the public GitHub tree. Do not commit `TOKEN-SPEND.md`, usage-dashboard screenshots, or usage CSVs. Track spend only in private/local project copies. Document this in README and `.gitignore`.

**Why:** Spend figures and billing UI screenshots are personal account data; they are not needed for reproducible harness evaluation and should not ship with public findings.

**Revisit:** Only if we later publish **anonymized aggregate** cost metrics from controlled evals (no personal dashboard dumps).
