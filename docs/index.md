# 📘 Friday Documentation

Welcome to **Friday** — a practical, modular framework for building **reliable multi-agent AI workflows** with:

- deterministic orchestration  
- pluggable agents  
- evaluation hooks  
- observability integration  
- enterprise-ready design  

Friday is created and maintained by **The AI Integrators**.

---

## 🚀 What Is Friday?

Friday is a lightweight but powerful orchestration engine designed for **real-world AI systems** where reliability, traceability, and evaluation matter.

It is built on three core pillars:

### **1. friday-core**  
The orchestrator, agent abstractions, router, and event loop.

### **2. friday-evaluation**  
Evaluation patterns and scoring logic for enterprise workflows.

### **3. friday-observability**  
Tracing, logging, and analytics integrations (e.g., Langfuse).

---

## 🧩 Why Friday Exists

Most agent frameworks focus on:

❌ demos  
❌ autonomous agents  
❌ non-deterministic routing  

But enterprises need:

✔ predictable workflows  
✔ auditability  
✔ evaluation gates  
✔ modular components  
✔ production-ready architecture  

Friday provides the structure needed to operationalize multi-agent systems safely and reliably.

---

## 🏛 Architecture Overview

```
           ┌───────────────────┐
           │   Observability   │
           └─────────▲─────────┘
                     │
                     │
        ┌────────────┴────────────┐
        │      Orchestrator       │
        │       (friday-core)     │
        └────────────▲────────────┘
                     │
                     │
              ┌──────┴──────┐
              │  Evaluation  │
              └──────────────┘
```

See **ARCHITECTURE.md** for a deeper technical breakdown.

---

## 🧭 Getting Started

### Install (future PyPI release)

```bash
pip install friday
```

For now, clone the repositories:

```bash
git clone https://github.com/theaiintegrators/friday-core.git
git clone https://github.com/theaiintegrators/friday-evaluation.git
git clone https://github.com/theaiintegrators/friday-observability.git
```

---

## 🧪 Example Workflow

A simple two-agent workflow in Friday Core:

```python
from friday import Orchestrator, Agent, Event

class AgentA(Agent):
    def run(self, event: Event):
        return Event(content="Hello from A", next="agent_b")

class AgentB(Agent):
    def run(self, event: Event):
        return Event(content="Hello from B", next=None)

agents = {
    "agent_a": AgentA(),
    "agent_b": AgentB()
}

orchestrator = Orchestrator(agents)
result = orchestrator.run("start")
print(result)
```

---

## 📂 Repository Structure

```
friday-core/
friday-evaluation/
friday-observability/
.github/
docs/
```

---

## 📜 Governance & Policies

Friday follows open-source best practices:

- [CONTRIBUTING](../CONTRIBUTING.md)  
- [CODE OF CONDUCT](../CODE_OF_CONDUCT.md)  
- [SECURITY](../SECURITY.md)  
- [LICENSE](../LICENSE)  

---

## 🌟 Roadmap

Upcoming enhancements:

- Workflow visualizer  
- Parallel agent execution  
- YAML-defined workflows  
- Langfuse auto-enriched traces  
- Built-in safety evaluators  
- Friday CLI  

---

## ❤️ Maintainers

Friday is developed by:

**The AI Integrators**  
https://theaiintegrators.ai
