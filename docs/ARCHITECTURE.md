# 🏛 **Friday Architecture (Conceptual Overview)**

*Deep Technical Overview of the Full Friday Multi-Agent Ecosystem*

Friday is designed around a simple but powerful idea:

> **Multi-agent systems must be predictable, observable, and testable
> --- or they cannot be used in enterprises.**

This document describes the **conceptual architecture for the full
Friday ecosystem**
(public + enterprise-grade design).
The **public open-core repositories** provide simplified modules aligned
with the same philosophy, while certain enterprise-only components
(e.g., orchestrator internals, router policies, event model) are *not
included* in the public edition.

------------------------------------------------------------------------

# 1️⃣ Core Design Philosophy

Friday is built using six foundational principles that guide both the
**public modules** and the **enterprise architecture**.

## **1. Determinism**

Agent routing should never rely on opaque model behaviour.
Developers must know:

-   which agent runs next
-   why it runs
-   what the state transitions are

## **2. Minimalism**

Friday avoids monolithic "mega-frameworks."
Instead, it embraces:

-   small components
-   simple abstractions
-   clear boundaries
-   clean orchestration

## **3. Transparency**

Enterprise AI systems require auditability:

-   every event
-   every agent
-   every decision
-   every input/output
-   every error

must be traceable.

## **4. Extensibility**

Each layer (orchestration, evaluation, observability) should be
replaceable or pluggable without rewriting core logic.

## **5. Enterprise Reliability**

Friday is built for:

-   evaluation gates
-   safe-guards
-   fallback routing
-   compliance
-   reproducibility

## **6. Developer Experience**

A workflow should be:

-   easy to debug
-   easy to reason about
-   easy to test
-   easy to extend

------------------------------------------------------------------------

# 2️⃣ Conceptual Architecture (Full Friday Ecosystem)

The FULL Friday architecture --- including the enterprise-only
components **not included** in the public repos --- looks like this:

               ┌───────────────────┐
               │   Observability   │
               │ (friday-observ.)  │
               └─────────▲─────────┘
                         │
            ┌────────────┴────────────┐
            │      Orchestrator       │
            │   (enterprise concept)  │
            └────────────▲────────────┘
                         │
                  ┌──────┴─────────┐
                  │   Evaluation   │
                  │ (friday-eval.) │
                  └────────────────┘

### How the conceptual architecture flows:

1.  An **event** enters the orchestrator
2.  The router selects an **agent**
3.  The agent processes the event
4.  The evaluator validates correctness
5.  Observability records all data
6.  The orchestrator moves to the next step

------------------------------------------------------------------------

# 3️⃣ Components (Conceptual + Public Open-Core Mapping)

This section explains the **full conceptual component** and shows **how
the public repos relate**.

------------------------------------------------------------------------

## **3.1 Orchestrator (Conceptual -- Enterprise Component)**

*Not included in public edition.*

The conceptual orchestrator manages:

-   event flow
-   agent registry
-   routing rules
-   state transitions
-   evaluation + observability hooks

The public `friday-core` repo demonstrates the **philosophy** via a
simplified LangGraph workflow, without exposing internal enterprise
logic.

------------------------------------------------------------------------

## **3.2 Router (Conceptual -- Enterprise Component)**

Routing considerations include:

-   deterministic agent routing
-   A2A patterns
-   explicit `next` transitions
-   optional dynamic routing policies

The public edition includes **deterministic linear routing** via
LangGraph node transitions.

------------------------------------------------------------------------

## **3.3 Agent (Shared Concept)**

An agent implements:

``` python
def run(self, event):
    ...
```

Principles:

-   single responsibility
-   typed input/output
-   predictable behaviour

The public edition includes simple demo agents (`SearchAgent`,
`MathAgent`) that demonstrate the interface pattern.

------------------------------------------------------------------------

## **3.4 Event Model (Conceptual -- Enterprise Component)**

Events contain:

-   content
-   state
-   metadata
-   routing control

This powers:

-   determinism
-   replay
-   observability
-   debugging

The public edition uses simplified state passing through LangGraph.

------------------------------------------------------------------------

## **3.5 Evaluation Layer (Public: friday-evaluation)**

Ensures reliability through:

-   rule-based evaluation
-   dataset-driven scoring
-   structure validation
-   simple scoring rubrics

The public repo provides modular evaluation tools that mirror the
enterprise design goals without exposing private evaluation logic.

------------------------------------------------------------------------

## **3.6 Observability Layer (Public: friday-observability)**

Provides:

-   trace recording
-   latency and error metrics
-   Grafana dashboards
-   Prometheus integration
-   future Langfuse compatibility

The public repo includes a complete metrics + dashboard stack.

------------------------------------------------------------------------

# 4️⃣ Future Extensions (Roadmap)

These conceptual features guide future development:

-   parallel agent execution
-   YAML-based workflow definitions
-   fallback routing
-   workflow visualization
-   OpenTelemetry support
-   Langfuse auto-enrichment
-   LLM-based evaluators (optional)
-   richer agent templates
-   workflow-level evaluation

------------------------------------------------------------------------

# 5️⃣ Why This Architecture Works

  Requirement             Friday Solution
  ----------------------- -------------------------
  Deterministic routing   Explicit routing design
  Traceability            Observability + logs
  Reliability             Evaluation gates
  Extensibility           Modular open-core repos
  Debugging               Structured traces
  Enterprise readiness    Clean workflows

Friday balances:

-   open-core simplicity
-   enterprise-grade concepts
-   and safe modular separation

The public repos demonstrate the foundations without exposing private
training, routing, or enterprise logic.

------------------------------------------------------------------------

# ⭐ **Summary**

Friday is a **conceptual multi-agent architecture** designed for:

-   predictable workflows
-   observable pipelines
-   testable AI behaviour
-   modular system design

The **public repositories** (`friday-core`, `friday-evaluation`,
`friday-observability`)
provide an **open-core demonstration** of the principles,
while the **full enterprise architecture** extends these concepts with
additional components not included in the public release.

This creates a perfect balance between:

-   **demonstrating your architecture skills**, and
-   **protecting private, enterprise-only intelligence.**
