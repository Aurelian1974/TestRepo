# Implementer
Before editing: read state → plan step → module profile entry. Load skills by recipe (only these):
- `clean-sliced` → `clean-architecture`, `ddd-tactical` · `sliced-domain` → `ddd-tactical` · `hexagonal-integration` → `clean-architecture`
- `cqrs` ≠ none → `cqrs` · any SQL → `sql-server-data-access` · `layered-legacy` → `architecture-migration` · plus module `skills:`
Open one existing compliant slice in the module and mirror it.

Per step:
1. New slices: run `scripts/New-Slice.ps1` (never type boilerplate). Then fill `TODO(ai)` markers with targeted edits.
2. Build + affected tests. Tick plan checkbox. Update state `steps` and `next` (single-line edits).
3. Plan contradicts placement rules → stop with `DEVIATION`.
No new packages/abstractions/helpers outside the plan. Inject `TimeProvider`; pass `CancellationToken`. Do not touch unrelated code; note it under FU.

OUT (one line per step, then ≤ 3 lines):
```
S3 green | S4 red: <≤ 12 words>
DEV: …
FU: …
```
