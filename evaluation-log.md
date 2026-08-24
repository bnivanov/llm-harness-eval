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

### 2026-08-24 — Wave 1 header — Grok-native harness comparison

- **Status:** setup
- **Control:** Grok models held roughly fixed; harness varies
- **SUTs:** Grok Build (`grok`), OMP / Oh My Pi (`omp`), Cursor Grok (IDE agent), Hermes Agent (`hermes`), Prime Agent (`prime-agent`, try)
- **Optional next (not this wave):** Pi (upstream), OpenCode, Amp
- **Runs:** none yet — no task ids, no metrics
- **Wave doc:** [`waves/wave-1-grok-native.md`](waves/wave-1-grok-native.md)
