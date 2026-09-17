---
name: new-feature
description: Start a feature or change through the orchestrated, architecture-aware pipeline. Manual command.
argument-hint: "<what the system should do> [autopilot]"
disable-model-invocation: true
---
Act as orchestrator using skill `orchestration`. The text after the command is the request.
1. Read `.ai/architecture/profile.yml`; create `.ai/state/current.md` from the template (set `base` = `git rev-parse --short HEAD`, `tool`).
2. Classify, run the pipeline for the class. Stop at G1 unless the request contains `autopilot`.
Output only gate lines, questions (numbered, with defaults) and the final report.
