# Mindcraft Eight-Week Roadmap

This roadmap is optimized for a solo maintainer using coding agents. It uses two estimate sizes: **3 points** for bounded single-module work and **5 points** for cross-module work requiring integration validation. GitHub Issues in [`logan-crosby/mindcraft`](https://github.com/logan-crosby/mindcraft/issues) are the delivery source of truth.

## Strategic Pillars

### Runtime Reliability & Verification

Build deterministic quality gates, then make agent lifecycle failures bounded, observable, and recoverable.

Success means:

- Node 18 and 20 receive automated lint and regression coverage.
- Repeated failures cannot create unbounded restart or resource-leak loops.
- Maintainers can produce useful diagnostics without exposing secrets or prompts.

### Operator Experience & Distribution

Turn configuration failures into guided feedback, then provide repeatable local, CLI, Docker, and release installation paths.

Success means:

- Invalid configuration fails before agents spawn.
- Operators can diagnose readiness without launching Minecraft.
- Clean installations pass the same startup contract across supported environments.

## Sprint Plan

### [Sprint 1 — Quality Baseline](https://github.com/logan-crosby/mindcraft/milestone/1)

**June 22–July 5, 2026 · 18 points**

Epic: [Automated Quality Foundation](https://github.com/logan-crosby/mindcraft/issues/1)

| Story | Points |
| --- | ---: |
| [Add CI lint and Node 18/20 matrix](https://github.com/logan-crosby/mindcraft/issues/5) | 3 |
| [Introduce unit-test framework and shared fixtures](https://github.com/logan-crosby/mindcraft/issues/6) | 5 |
| [Build deterministic task smoke-test harness](https://github.com/logan-crosby/mindcraft/issues/7) | 5 |
| [Add lifecycle and configuration regression tests](https://github.com/logan-crosby/mindcraft/issues/8) | 5 |

### [Sprint 2 — Runtime Resilience](https://github.com/logan-crosby/mindcraft/milestone/2)

**July 6–19, 2026 · 18 points**

Epic: [Agent Lifecycle Reliability](https://github.com/logan-crosby/mindcraft/issues/2)

Depends on Sprint 1.

| Story | Points |
| --- | ---: |
| [Define structured lifecycle states and errors](https://github.com/logan-crosby/mindcraft/issues/9) | 5 |
| [Add bounded restart policy with backoff](https://github.com/logan-crosby/mindcraft/issues/10) | 5 |
| [Guarantee listener, timer, and action cleanup](https://github.com/logan-crosby/mindcraft/issues/11) | 5 |
| [Produce redacted diagnostic bundles](https://github.com/logan-crosby/mindcraft/issues/12) | 3 |

### [Sprint 3 — Guided Operations](https://github.com/logan-crosby/mindcraft/milestone/3)

**July 20–August 2, 2026 · 18 points**

Epic: [Configuration and Startup Experience](https://github.com/logan-crosby/mindcraft/issues/3)

Depends on Sprint 2.

| Story | Points |
| --- | ---: |
| [Add schema-based configuration validation](https://github.com/logan-crosby/mindcraft/issues/13) | 5 |
| [Add `npm run doctor` environment checks](https://github.com/logan-crosby/mindcraft/issues/14) | 5 |
| [Surface startup diagnostics in the dashboard](https://github.com/logan-crosby/mindcraft/issues/15) | 5 |
| [Rewrite setup and troubleshooting guidance](https://github.com/logan-crosby/mindcraft/issues/16) | 3 |

### [Sprint 4 — Repeatable Distribution](https://github.com/logan-crosby/mindcraft/milestone/4)

**August 3–16, 2026 · 18 points**

Epic: [Installable and Reproducible Releases](https://github.com/logan-crosby/mindcraft/issues/4)

Depends on Sprint 3.

| Story | Points |
| --- | ---: |
| [Define supported Node and package contract](https://github.com/logan-crosby/mindcraft/issues/17) | 3 |
| [Add packaged CLI and startup entrypoint](https://github.com/logan-crosby/mindcraft/issues/18) | 5 |
| [Add Docker health checks and local parity validation](https://github.com/logan-crosby/mindcraft/issues/19) | 5 |
| [Add release installation smoke matrix](https://github.com/logan-crosby/mindcraft/issues/20) | 5 |

## Delivery Rules

- Complete predecessor issues before removing `status:blocked`.
- Keep each sprint at 18 committed points; move incomplete stories forward rather than expanding scope.
- Every story must satisfy its GitHub acceptance checklist and include verification evidence.
- Submit upstream pull requests separately after a story is complete and validated on the fork.
