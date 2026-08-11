Yehor Kaliberda 🇩🇰

AI Directive Engineering & Founder · Aarhus, Denmark

I build autonomous engineering agents that treat codebases as semantic graphs — and ship the results as verified, reviewable Pull Requests.

## Products

### Symbiote — Autonomous Type Annotation Engine

Symbiote maps a Python repository into a typed AST dependency graph and runs a multi-agent Mirror Pass that writes PEP 484 annotations under collision-free file locks. Delivers a single reviewable PR with 0 pyright errors confirmed before it leaves the system.

**Architecture highlights**

| Component | What it does |
| --- | --- |
| AST graph (tree-sitter + NetworkX) | Structural map of every import edge and call relationship |
| Bouncer lock layer | Computes exact blast radius before any write; blocks concurrent collisions mechanically |
| Nanosecond audit trail | Every agent action logged — full trace, reproducible execution |
| Pydantic schema gates | Perception → Reasoning → Action loop; prevents structural drift |

Stack: Python 3.12 · tree-sitter · NetworkX · Anthropic Claude · Pydantic

### Patchward — Autonomous Security Fix Pipeline

Patchward scans your Python and JavaScript codebase for security findings, triages them, generates a targeted fix, and opens one bounded draft PR — with a receipt that states exactly which gates ran.

```
uv tool install patchward
patchward fix --repo .
```

**Pipeline**

| Stage | Detail |
| --- | --- |
| Scan | Semgrep · Bandit · pip-audit · Trivy · ESLint → unified SARIF |
| Triage | AI analyst scores severity, filters noise, ranks by exploitability |
| Fix-Gen | Claude generates minimal, surgical patches |
| Verifier (3 gates) | Re-scan · diff bounds · test suite — every PR states exactly which gates ran |

Static analysis runs entirely on-premise, in a network-isolated sandbox. The triage and fix-generation stages call the Anthropic API and read repository content to do their job — the verifier itself is deterministic and auditable.

Stack: Python 3.12 · Semgrep · Bandit · pip-audit · Trivy · Anthropic Claude · GitPython

**→ [patchward.dev](https://patchward.dev)**

### FixProve — Deterministic CI Gate for AI-Written Code

AI assistants write code that looks right and calls things that don't exist — a renamed method, a package that was never installed. FixProve resolves every import, call, and attribute your AI wrote against what's actually installed in your project. Deterministically. No model in the analysis loop.

```
pip install fixprove
npm install -g fixprove
fixprove check /path/to/your/project
```

**Example**

| Your AI wrote | FixProve catches |
| --- | --- |
| `pd.read_exel("data.xlsx")` | `read_exel` doesn't exist on your installed pandas — did you mean `read_excel`? |
| `from fastapi_helpers import cache` | `fastapi_helpers` isn't installed in this environment |

Hard cases — dynamic imports, `__getattr__`, C-extension builtins, a crashing subprocess — degrade to an explicit flag. Never a guess, never a false positive.

Stack: Python · TypeScript/JavaScript · AST resolution

**→ [fixprove.dev](https://fixprove.dev)**

Status: live on PyPI and npm, running as a GitHub App check on internal pull requests. Independent from CallMed AI — pre-traction, built and verified, not yet publicly marketed.

## Track Record

| Repository | Type | Result |
| --- | --- | --- |
| [mpfb2](https://github.com/makehumancommunity/mpfb2) | Type annotations (Symbiote) | Multiple PRs merged (#377, #378 and following) |
| [aeon-timeseries/aeon](https://github.com/aeon-toolkit/aeon) | Type annotations (Symbiote) | PR #235 merged |
| [domainaware/checkdmarc](https://github.com/domainaware/checkdmarc) | Security fix (Patchward) | Finding credited by the maintainer; closed as superseded by the maintainer's own narrower fix, shipped in v5.17.3 |

PRs generated autonomously and verified before submission. Full run-by-run record: [callmedai.com](https://callmedai.com).

## How I Think About Code

Every import is an edge, and every function call is a relationship. Refactoring isn't just applying diffs—it's mutating a graph.

That’s the whole premise behind the agents I build. They reason about underlying structure instead of endlessly reshuffling blind bytes, which is frankly more than I can say for most human stand-ups I’ve sat through.

The practical payoff is simple: when an agent actually grasps why two nodes are connected, its changes become provably safe, not just syntactically valid.

## Connect

🌐 Website — [callmedai.com](https://callmedai.com) · [patchward.dev](https://patchward.dev) · [fixprove.dev](https://fixprove.dev)
💼 LinkedIn — [linkedin.com/in/yehorkaliberda](https://linkedin.com/in/yehorkaliberda)
✉️ Email — yehor@yehor.ai
