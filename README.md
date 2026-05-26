# Yehor Kaliberda 🇩🇰
**AI Systems Architect & Founder** <br>
📍 Aarhus, Denmark <br>
**Focus:** Autonomous Multi-Agent Infrastructure, Semantic Codebase Evolution, Voice AI Ecosystems

---

### 🧠 How I Think About Code
I treat codebases as living semantic graphs, not just flat text files. Every import is an edge, every function call is a relationship. When we refactor something, we're really mutating a graph—not just blindly running diffs against bytes. 

I design autonomous systems based on this exact idea. The goal is to build self-governing agents that can solve complex engineering problems without needing constant human intervention.

### 🛠 What I'm Building

#### 1. Symbiote Core Engine
I built this engine to let multiple AI agents safely edit the same codebase at the same time. The core challenge wasn't just getting the agents to write code, but keeping them from stepping on each other's toes.
* **AST Mapping:** Instead of letting agents guess where things are, the system uses custom tree-sitter pipelines to parse the whole repository into a structural NetworkX graph.
* **Governed Concurrency:** I wrote a persistent control layer that checks the exact blast radius of every write operation. If two agents try to mutate the same space, the system mechanically blocks the collision.
* **Auditing:** Every single agent action is logged with nanosecond precision so we can actually trace what happened and guarantee the execution was clean.
* **Safety Boundaries:** Left to their own devices, agents will eventually corrupt a codebase. I enforce a strict Perception → Reasoning → Action loop, locked down by Pydantic schemas, to prevent structural decay.

#### 2. CallMed AI
An AI voice receptionist platform built for medical clinics and med spas.
* Handles inbound workflow routing, patient triage, and automated scheduling.
* The backend is complex, but the user experience is intentionally stripped down. We went with a clean, Nordic minimal design. In healthcare, trust is everything, and an overly flashy or complicated interface just feels risky.

### 📈 Testing in the wild
It's one thing to build an autonomous architecture; it's another to let it loose. I actively test my systems against real-world, production-grade open-source environments to see if they hold up.
* **Automated Refactoring:** I've been running headless agents to push automated type-hint saturation and PEP 484 compliance across branches.
* **Strict Guardrails:** The agents are calibrated to strictly respect PEP 8 spacing and docstring rules, ensuring the output actually looks like human-written code rather than an algorithmic dump.

### 📬 Connect
* **LinkedIn:** [in/yehorkaliberda](https://www.linkedin.com/in/yehorkaliberda/)
