# 🌐 The AI Integrators
### _Multi-Agent Orchestration • Evaluation • Observability_

Welcome to **The AI Integrators** — an open-source initiative focused on building **modular, enterprise-ready frameworks for multi-agent AI systems**.

Our mission is to make AI workflows:

- **Reliable**  
- **Testable**  
- **Observable**  
- **Deployable in real enterprises**

The Friday ecosystem achieves this through clean abstractions, modular components, and strong evaluation & observability foundations.

---

# 🧩 The Friday Ecosystem

Friday is a growing set of libraries designed to help developers build **deterministic, debuggable multi-agent systems**.

---

### 🔹 friday-core  
Multi-agent orchestration engine  
→ Event loop, routing, agent interface  
→ The “brain” of the workflow  

**Repo:** https://github.com/theaiintegrators/friday-core

---

### 🔹 friday-evaluation  
Evaluation pipeline for validating agent outputs  
→ Rule-based, LLM-based, and composite evaluators  
→ DeepEval integration  

**Repo:** https://github.com/theaiintegrators/friday-evaluation

---

### 🔹 friday-observability  
Tracing, logging & debugging  
→ Structured agent traces  
→ Langfuse integration  
→ Metrics & workflow diagnostics  

**Repo:** https://github.com/theaiintegrators/friday-observability

---

# Friday Architecture (High-Level)

```
           ┌───────────────────┐
           │   Observability   │
           └─────────▲─────────┘
                     │
                     │
        ┌────────────┴────────────┐
        │      Orchestration      │
        │      (friday-core)      │
        └────────────▲────────────┘
                     │
                     │
              ┌──────┴───────┐
              │  Evaluation  │
              └──────────────┘
```

The three components form a cohesive triangle:

- **Core** handles agent execution  
- **Evaluation** enforces correctness  
- **Observability** ensures transparency  

This creates a workflow that is both **powerful** and **controlled**.

---

# 🚀 Why Friday?

Modern AI applications require more than a single model call.

Enterprises need:

- multi-step reasoning  
- task delegation  
- consistent routing  
- correctness guarantees  
- observability for debugging  
- real metrics  
- structured outputs  

Existing frameworks often lack these foundations, making it difficult to run agent workflows **safely**.

Friday was created to fill this gap with:

- Clean architecture  
- Extensibility  
- Production readiness  
- Determinism & reliability  
- First-class evaluation & tracing  

---

# 📦 Roadmap

- [ ] Publish friday-core on PyPI  
- [ ] Add workflow visualisation UI  
- [ ] Add Langfuse auto-enrichment  
- [ ] Add OpenTelemetry support  
- [ ] Add YAML-defined AI pipelines  
- [ ] Add built-in agent templates  
- [ ] Example reference workflows  

---

# 🤝 Contributing

Friday is under active development.  
Contributions, suggestions, and issues are welcome.

Please open discussions or issues in the respective repositories.

---

# 📄 License

All Friday projects are released under the **MIT License**.
