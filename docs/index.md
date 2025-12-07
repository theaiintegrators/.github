# 📘 Friday Documentation

*Conceptual Overview of the Friday Multi-Agent Ecosystem*

Friday is a modular, open-core framework for building **reliable
multi-agent AI workflows** with:

-   predictable execution
-   clean agent interfaces
-   evaluation-friendly design
-   observability integrations
-   enterprise-ready concepts

This documentation outlines the **conceptual architecture** of Friday
(public + enterprise design), while the public repositories provide
**simplified open-core implementations** aligned with these principles.

------------------------------------------------------------------------

## 🚀 What Is Friday?

Friday is a practical multi-agent architecture designed for **real-world
AI systems** where:

-   determinism
-   traceability
-   testing
-   observability
-   modularity

are essential.

The ecosystem consists of three public modules:

### **1. friday-core (open-core orchestration example)**

A simplified LangGraph-based workflow demonstrating deterministic state
flow and agent logic.

### **2. friday-evaluation**

Task definitions, datasets, scoring rubrics, and evaluation utilities.

### **3. friday-observability**

Prometheus + Grafana dashboards and metrics emitter for monitoring agent
systems.

These public modules illustrate Friday's philosophy without exposing
enterprise-only implementations such as the internal orchestrator,
router, or event model.

------------------------------------------------------------------------

## 🧩 Why Friday Exists

Most agent frameworks focus on:

❌ flashy demos
❌ autonomous agents
❌ unpredictable routing

But enterprise workflows require:

✔ determinism
✔ safety
✔ evaluation gates
✔ auditability
✔ observability
✔ reproducibility

Friday provides a structured way to design such systems --- with public
modules demonstrating the patterns without revealing proprietary
internals.

------------------------------------------------------------------------

## 🏛 Conceptual Architecture Overview

               ┌───────────────────┐
               │   Observability   │
               │ (open-core)       │
               └─────────▲─────────┘
                         │
            ┌────────────┴────────────┐
            │      Orchestrator       │
            │   (enterprise concept)  │
            └────────────▲────────────┘
                         │
                  ┌──────┴─────────┐
                  │   Evaluation   │
                  │  (open-core)   │
                  └────────────────┘

The public repos show the **philosophy** (determinism, transparency,
modularity),
while certain enterprise features (dynamic routing, event model,
advanced agents) are not included.

See **ARCHITECTURE.md** for a deeper conceptual breakdown.

------------------------------------------------------------------------

## 🧭 Getting Started (Public Open-Core)

Clone the repositories:

``` bash
git clone https://github.com/theaiintegrators/friday-core.git
git clone https://github.com/theaiintegrators/friday-evaluation.git
git clone https://github.com/theaiintegrators/friday-observability.git
```

### Example (public friday-core sample)

``` bash
cd friday-core
python -m examples.run_demo
```

This demonstrates a deterministic state-flow example using LangGraph.

------------------------------------------------------------------------

## 📂 Repository Structure

    friday-core/
    friday-evaluation/
    friday-observability/
    .github/
    docs/

-   `/docs` → ecosystem-level conceptual docs
-   `/friday-core` → open-core orchestration example
-   `/friday-evaluation` → evaluation utilities
-   `/friday-observability` → metrics and dashboards

------------------------------------------------------------------------

## 🌟 Roadmap

-   Workflow visualizer
-   Parallel agent execution
-   YAML-defined workflows
-   OpenTelemetry support
-   Langfuse auto-enrichment
-   LLM-based evaluators (optional)
-   Friday CLI

------------------------------------------------------------------------

## ❤️ Maintainers

Friday is developed and maintained by:

**The AI Integrators**
https://theaiintegrators.ai
