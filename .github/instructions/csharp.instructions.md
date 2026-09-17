---
name: csharp-standards
description: "C# / .NET coding standards applied to all C# files."
applyTo: "**/*.cs"
---
<!-- GENERATED from .ai/kit by scripts/Build-AiKit.ps1 — edit the sources, not this file -->
# C# standards

- Target the runtime in `profile.yml`; use current language features where they reduce noise
  (primary constructors for DI, collection expressions, `required`, file-scoped namespaces, raw strings for SQL).
- `sealed` by default; `internal` by default inside modules; public only for Contracts and `{M}Module`.
- Nullable reference types enabled; no `!` suppression without a comment stating the invariant.
- Async all the way: `Async` suffix, `CancellationToken ct` as last parameter and passed through; no `.Result`/`.Wait()`.
- Time via injected `TimeProvider`; ids via `Guid.CreateVersion7()` or strongly-typed ids.
- Expected failures → `Result`/`Error` (when profile `error_model: result`); exceptions for faults only.
- Records for commands, queries, responses, events, value objects. No mutable DTOs.
- Logging: structured templates (`"Invoice {InvoiceId} issued"`), no string interpolation, no personal data.
- No `static` mutable state, no service locator (`IServiceProvider` in business code).
- LINQ over EF: project with `Select` for reads; never `ToList()` before filtering.
- Names: business language from the module; no `Manager`, `Helper`, `Util`, `Processor` suffixes.
- Comments explain why, not what. XML docs only on Contracts.
