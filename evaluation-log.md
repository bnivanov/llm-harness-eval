# Evaluation log

Running log of **what we evaluate, when, and outcome**. Newest first.

Do not record scores until a run happens. Wave headers may exist in `setup` with empty results.

## Template

```
### YYYY-MM-DD — <harness> — <task id>
- Window: ...
- Model / native routing: ...
- Task: ...
- Metrics: success · latency · tokens/cost · notes
- Artifacts: links/paths
- Result: pass/fail/partial
```

## Entries

### 2026-08-24 — Wave 1 header — Grok-native cluster + matrix expansion

- **Status:** setup
- **Control:** Grok-native cluster — Grok models held roughly fixed; harness varies. Expansion SUTs use native routing (not claimed Grok-only).
- **SUTs (Grok-native cluster):** Grok Build (`grok`), Pi (`pi`, OMP upstream/control), OMP / Oh My Pi (`omp`), Cursor Grok (IDE agent), Hermes Agent (`hermes`), Prime Agent (`prime-agent`, try)
- **SUTs (matrix expansion):** Amp (`amp`; own routing), FX (`fx`; Vercel / AI Gateway), Codex CLI (`codex`; OpenAI-native baseline)
- **Optional next (not this wave):** OpenCode
- **Runs:** none yet — no task ids, no metrics, no install success logged
- **Wave doc:** [`waves/wave-1-grok-native.md`](waves/wave-1-grok-native.md)
