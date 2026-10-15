# Managed Agents repository skill fixture

Public, synthetic fixture for [managed-agents-wire-recordings](https://github.com/OpenSDLC-Dev/managed-agents-wire-recordings) issues #22 and #23. No credentials or private data are stored here. The `main` branch contains valid, malformed, case-variant and nested skill layouts; the `checkout-alt` branch has a different root skill to test `github_repository.checkout`.

The `announcement-followup` branch has 30 root skills: 28 numbered controls, one directory/frontmatter name mismatch, and one description of exactly 3,000 characters. It retains the nested `packages/x` skill from `checkout-alt`. This branch supports recordings issue #26.

The skill bodies are harmless identifiers. Their purpose is to reveal discovery and announcement behavior, not to make the agent perform external actions.
