# Managed Agents repository skill fixture

Public, synthetic fixture for [managed-agents-wire-recordings](https://github.com/OpenSDLC-Dev/managed-agents-wire-recordings) issues #22, #23 and #26. No credentials or private data are stored here. The `main` branch contains valid, malformed, case-variant and nested skill layouts; the `checkout-alt` branch has a different root skill to test `github_repository.checkout`.

The skill bodies are harmless identifiers. Their purpose is to reveal discovery and announcement behavior, not to make the agent perform external actions.

## Fixture branches

| Branch | Root `.claude/skills` layout | Purpose |
|---|---|---|
| `main` | `alpha`, `pdf`, `broken`, `nodesc`, lowercase `lower/skill.md`, and valid `boundary-{2000,3000,5000,10000}` | Combined scan, same-name `pdf` comparison, and valid long-description boundary controls |
| `checkout-alt` | `beta` | Branch checkout, nested `packages/x` read and mount rebasing |
| `alpha-only`, `pdf-only`, `nodesc-only`, `lower-only` | The named case only | Single-layout controls |
| `broken-control`, `nodesc-control`, `lower-control` | `alpha` plus the named case | Malformed or filename control beside a valid skill |
| `two-valid`, `valid-controls` | `alpha` + `pdf`; the latter also has lowercase `lower/skill.md` | Multi-skill controls |
| `alpha-on-alt`, `beta-copy` | One valid skill each | Cross-check branch history versus skill name |

Every branch retains `packages/x/.claude/skills/inner/SKILL.md` and `packages/x/probe.txt` for the nested-subtree test. The recording's [findings](https://github.com/OpenSDLC-Dev/managed-agents-wire-recordings/blob/main/2026-10-13-repo-mount-skills/FINDINGS.md) cite exact request indexes and distinguish direct observations from the agent's report of hidden prompt text.

The `boundary-N` skills have real-newline YAML frontmatter. Each `description` is exactly N ASCII characters, beginning with `REC26_BEGIN_N_` and ending with `_REC26_END_N`. They are synthetic controls for [recordings #26](https://github.com/OpenSDLC-Dev/managed-agents-wire-recordings/issues/26).
