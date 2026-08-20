# heca-issues

Issue tracker for [heca](https://github.com/getheca/heca), the agent-orchestration platform.

This repository exists so internal users **without access to the main `getheca/heca` repository** can still report bugs, request features, and propose work items. Maintainers triage issues filed here and mirror accepted ones into the main repository.

## How to file an issue

1. Go to [Issues → New issue](https://github.com/getheca/heca-issues/issues/new/choose).
2. Pick the template that fits:
   - **Bug report** — something is broken or behaving unexpectedly.
   - **Feature request** — you want heca to do something it does not do today.
   - **Work item** — a fully specified, implementation-ready task (used by maintainers and agents; use this only if you can fill in scope and acceptance criteria).
3. Fill in every required field. The more self-contained the issue, the faster it gets triaged.

## What makes a good issue

Issues in the heca project are expected to be **self-contained**: someone (or an agent) picking up the issue should not need to ask you follow-up questions or consult external context. Concretely:

- **One issue per problem.** Do not bundle unrelated bugs or requests.
- **Exact version.** heca uses nightly versioning (`0.1.0-nightly-YYYYMMDD-N`). Find it in the app's About screen or via `heca --version`.
- **Platform and surface.** Desktop (macOS / Linux / Windows), mobile (iOS / Android), web, CLI, or daemon — behavior can differ per surface.
- **Provider, if relevant.** claude / codex / grok / opencode / antigravity — many behaviors are provider-specific.
- **Reproduction steps.** Numbered steps from a clean state. "It sometimes breaks" is not actionable; "spawn an agent, kill the daemon, reopen the app" is.
- **Expected vs. actual.** State both explicitly.
- **Logs and screenshots.** Attach what you have.

### Redact before you paste

Never paste secrets into an issue: API keys, tokens, passwords, JWTs, relay pairing codes, or file paths that reveal private information. Review logs and screenshots before attaching them and replace sensitive values with `<REDACTED>`.

## Labels

Maintainers apply labels during triage; you do not need to set them yourself. The taxonomy mirrors the main repository:

| Label | Meaning |
|---|---|
| `area:ui` | Flutter app UI (desktop / mobile / web) |
| `area:security` | Security-relevant behavior |
| `area:ci` | Build, release, or CI tooling |
| `area:docs` | Documentation |
| `area:testing` | Test coverage or test infrastructure |
| `crate:*` | A specific Rust crate (e.g. `crate:heca-daemon`) |
| `type:epic` | Large multi-issue effort |

New labels are added for new topics rather than overloading existing ones.

## What happens after you file

1. A maintainer triages the issue: reproduces it, applies labels, and asks for clarification if needed.
2. Accepted issues are mirrored into the main `getheca/heca` repository, restructured into the agent-takeover-grade format used there (Summary / Spec context / Scope / Implementation notes / Acceptance criteria / Dependencies / Definition of done).
3. The issue here is updated with a reference to the mirrored issue and closed when the fix or feature ships in a nightly.

## Dependencies between issues

If your issue depends on or blocks another issue in this tracker, declare it in the body text:

```
Depends on: #12
Blocks: #34
```
