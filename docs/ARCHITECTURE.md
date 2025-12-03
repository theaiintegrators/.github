# 🏛 Friday Architecture
_Deep Technical Overview of the Friday Multi-Agent Framework_

Friday is built around a simple but powerful idea:

> **Multi-agent systems must be predictable, observable, and testable — or they cannot be used in enterprises.**

Friday implements this through a modular architecture consisting of:

- **Orchestration** (`friday-core`)
- **Evaluation** (`friday-evaluation`)
- **Observability** (`friday-observability`)

---

# 1️⃣ Core Design Principles

Friday is designed with six principles:

### **1. Determinism**
Agent routing should not be “magical.”  
Developers must know exactly which agent runs next and why.

### **2. Minimalism**
The framework should be small, composable, and not tightly coupled to any specific model provider.

### **3. Transparency**
Every agent step, input, output, and routing decision must be traceable.

### **4. Extensibility**
Agents, evaluators, and observability providers should be fully pluggable.

### **5. Enterprise Reliability**
Support evaluation gates, safe-guards, fallback routing, and audit traces.

### **6. Developer Experience**
A workflow should be easy to reason about, easy to debug, and easy to test.

---

# 2️⃣ High-Level Architecture

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
              ┌──────┴───────┐
              │  Evaluation  │
              └──────────────┘
```

At runtime:

1. An **event** enters the orchestrator  
2. The router chooses the next **agent**  
3. The agent produces an output event  
4. Evaluation validates correctness  
5. Observability records all steps  
6. The workflow continues or stops  

---

# 3️⃣ Components in Detail

## **3.1 Orchestrator**

Coordinates the workflow:

- maintains agent registry  
- receives input events  
- executes the correct agent  
- merges event state  
- handles termination conditions  
- integrates evaluation + observability  

This is the “engine” of the system.

---

## **3.2 Router**

Determines which agent runs next.

Routing types:

- deterministic routing (`event.next`)  
- optional dynamic routing  
- future support for routing policies  

Routing must be explicit and predictable — unlike many agent frameworks which rely on LLM-based routing.

---

## **3.3 Agent**

Every agent implements:

```python
def run(self, event: Event) -> Event
```

Principles:

- single responsibility  
- no hidden state unless explicit  
- typed `Event` inputs and outputs  

Agents may wrap:

- LLM calls  
- API calls  
- internal logic  
- RAG pipelines  

---

## **3.4 Event Model**

Events carry:

- content  
- metadata  
- state  
- routing control (`next`)  

This provides:

- determinism  
- visibility  
- replayability  
- strong debugging  

---

## **3.5 Evaluation Layer**

Ensures reliability.

Types:

- rule-based  
- LLM-based  
- DeepEval integration  
- composite evaluators  

Runs after each agent to validate:

- correctness  
- safety  
- business constraints  
- structure  

---

## **3.6 Observability Layer**

Responsible for:

- trace logging  
- input/output recording  
- execution timing  
- error tracking  
- Langfuse integration  

This enables real debugging and workflow monitoring.

---

# 4️⃣ Future Extensions

- parallel agent execution  
- workflow visualization  
- OpenTelemetry support  
- Langfuse auto-enrichment  
- YAML pipeline definitions  
- agent templates  
- fallback routing  
- workflow-level evaluation  

---

# 5️⃣ Why This Architecture Works

| Requirement | Friday Solution |
|------------|-----------------|
| Deterministic routing | Explicit `next` in events |
| Traceability | Observability hooks |
| Reliability | Evaluation gates |
| Extensibility | Modular components |
| Debugging | Structured traces |
| Enterprise adoption | Clean, auditable workflows |

This enables both simple and complex multi-agent workflows.

---

# ⭐ Summary

Friday provides a foundational architecture for building reliable, observable, enterprise-grade AI workflows — something most agent frameworks lack.

