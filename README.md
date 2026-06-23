# Yehor Kaliberda 🇩🇰

**AI Systems Architect & Founder** · Aarhus, Denmark

I build autonomous engineering agents that treat codebases as semantic graphs — and ship the results as verified, reviewable Pull Requests.

---

## Products

### [Symbiote](https://callmedai.com) — Autonomous Type Annotation Engine

Symbiote maps a Python repository into a typed AST dependency graph and runs a multi-agent Mirror Pass that writes PEP 484 annotations under collision-free file locks. Delivers a single reviewable PR with **0 pyright errors confirmed** before it leaves the system.

**Architecture highlights**

| Component | What it does |
|---|---|
| AST graph (tree-sitter + NetworkX) | Structural map of every import edge and call relationship |
| Bouncer lock layer | Computes exact blast radius before any write; blocks concurrent collisions mechanically |
| Nanosecond audit trail | Every agent action logged — full trace, reproducible execution |
| Pydantic schema gates | Perception → Reasoning → Action loop; prevents structural drift |

**Stack:** Python 3.12 · tree-sitter · NetworkX · Anthropic Claude · Pydantic

---

### [RepoMend](https://callmedai.com) — Autonomous Security Fix Pipeline

RepoMend scans, triages, fixes, and verifies security vulnerabilities — entirely on-premise. One command from raw codebase to draft PR.

```
uv tool install repomend
repomend scan /path/to/repo
repomend fix
```

**Pipeline**

| Stage | Detail |
|---|---|
| Scan | Semgrep · Bandit · pip-audit · Trivy · ESLint → unified SARIF |
| Triage | AI analyst scores severity, filters noise, ranks by exploitability |
| Fix-Gen | Claude Sonnet generates minimal, surgical patches |
| Verifier (3 gates) | Re-scan · diff bounds · test suite — all must pass before PR opens |

Your code never leaves your infrastructure. The verifier is deterministic and auditable.

**Stack:** Python 3.12 · Semgrep · Bandit · pip-audit · Trivy · Anthropic Claude · GitPython

---

## Track Record

| Repository | Type | Result |
|---|---|---|
| [domainaware/checkdmarc](https://github.com/domainaware/checkdmarc) | Security fix (RepoMend) | PR merged — bare-except B110 |
| aeon-timeseries/aeon | Type annotations (Symbiote) | PRs #235+ merged |
| mpfb2 | Type annotations (Symbiote) | PRs #377, #378+ merged |

**7 PRs merged** into production open-source repositories. All generated autonomously and verified before submission.

---

## How I Think About Code

Every import is an edge. Every function call is a relationship. Refactoring is graph mutation — not diff application. The agents I build operate on this model: they reason about structure, not bytes.

The practical consequence: agents that understand *why* two nodes are connected can make changes that are provably safe, not just syntactically valid.

---

## Connect

| | |
|---|---|
| 🌐 Website | [callmedai.com](https://callmedai.com) |
| 💼 LinkedIn | [linkedin.com/in/yehorkaliberda](https://www.linkedin.com/in/yehorkaliberda/) |
| ✉️ Email | yehor@callmedai.com |
| 🐦 X / Twitter | [@hnmaster_](https://x.com/hnmaster_) |
