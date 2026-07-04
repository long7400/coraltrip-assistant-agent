# Triage Labels

This repo maps Matt Pocock's canonical triage roles to local markdown `Status:` strings.

| Canonical role | Local `Status:` value | Meaning |
|---|---|---|
| `needs-triage` | `needs-triage` | Maintainer or agent must evaluate the request. |
| `needs-info` | `needs-info` | Waiting on the reporter/user for missing information. |
| `ready-for-agent` | `ready-for-agent` | Fully specified and safe for an agent to implement without more human context. |
| `ready-for-human` | `ready-for-human` | Valid but requires human implementation or business judgment. |
| `wontfix` | `wontfix` | Will not be actioned; record the reason in the issue body. |

## Rules

- Exactly one triage status should be active per issue.
- Do not invent additional status strings unless the user explicitly changes this mapping.
- If a request changes product truth, update or link the relevant durable source: `spec-prd/`, `CONTEXT.md`, or `docs/adr/`.
