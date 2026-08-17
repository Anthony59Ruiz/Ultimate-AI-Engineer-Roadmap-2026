# AI Engineer Roadmap 2026 — Semiconductor Supply Chain & Logistics Edition 🔥🏭
### From Zero to Production-Grade AI for the Chip Supply Chain

A niche rewrite of the **Ultimate AI Engineer Roadmap 2026**, re-oriented for the
highest-stakes supply chain on earth: **semiconductors**. Same proven 17-phase
spine — every phase, project, and the capstone rebuilt around fabs, foundries,
OSAT, substrates, allocation, lead times, disruption risk, and export-control
compliance.

> Looking for the general track? See the main [README](../README.md).

---

## 📌 Why This Niche

Semiconductors are the most complex, most concentrated, and most geopolitically
contested supply chain in the world:

- **Lead times measured in months**, not days — a single missed forecast ripples
  across automotive, defense, medical, and consumer electronics.
- **Extreme supplier concentration** — a handful of fabs (TSMC, Samsung, Intel),
  one dominant EUV toolmaker (ASML), and a thin bench of substrate/ABF and
  specialty-chemical suppliers.
- **Allocation, not ordering** — in shortages, you don't buy chips, you get
  *allocated* them. Forecasting and supplier relationships become survival skills.
- **A compliance layer no other supply chain has** — export controls (EAR/ITAR,
  entity lists), the CHIPS Act, and data-sovereignty rules gate what can move
  where.

An AI engineer who can build forecasting, risk, and disruption-monitoring systems
for **this** domain is rare and highly paid. That's what this roadmap builds.

---

## 🧭 Who Hires For This

- Fabs & IDMs (TSMC, Intel, Samsung, GlobalFoundries, Micron, TI)
- OSAT / assembly & test (ASE, Amkor, JCET)
- Equipment & materials (ASML, Applied Materials, Lam, substrate/ABF makers)
- Fabless & systems companies managing chip supply (NVIDIA, Apple, AMD, Qualcomm)
- Distributors & brokers (Arrow, Avnet, and the gray market)
- Supply-chain analytics & control-tower vendors, ERP/planning platforms, and
  logistics/freight-forwarding firms serving the electronics sector

---

## 📌 How to Use This Roadmap

```
NEW TO AI       → Phase 0 → 1 → 2 → 3 (foundation-first)
SUPPLY-CHAIN PRO → Phase 0 → 1 → 3 → 6 → 8 → 9 (bring your domain, add AI)
AI ENGINEER      → Phase 6 → 7 → 8 → 9 → 12 → 13 (bring your AI, add the domain)
```

Each phase ends with **Project-Based Learning**, always three tiers:
- 🟢 **Easy** — build confidence, reinforce fundamentals
- 🟡 **Medium** — real-world patterns, production thinking
- 🔴 **Hard** — production-grade, multi-system, scalable

**51 projects total.** The capstone is a full **Semiconductor Supply-Chain
Control Tower** platform.

---

## 🗺️ PHASE 0 - Mindset & Orientation

### What is an AI Engineer in Semiconductor Supply Chain?

You are the bridge between AI models and the systems that keep chips flowing. You:

- Turn messy supply-chain data (EDI, BOMs, ERP tables, PDFs, news) into signal
- Build demand/allocation forecasts, lead-time predictors, and risk scores
- Ship disruption-monitoring and procurement copilots that planners actually use
- Bake export-control and data-sovereignty constraints into every system
- Know when a simple time-series model beats an LLM — and when it doesn't

### AI Engineer vs. Supply-Chain Data Scientist

| AI Engineer (this track) | Supply-Chain Data Scientist |
|---|---|
| Integrates & ships AI into planning systems | Builds statistical/optimization models |
| LLMs, RAG, agents, MLOps | Forecasting research, OR, econometrics |
| Product + production focus | Analysis + insight focus |
| **You are this** | Adjacent partner role |

### Market Reality 2026

Skills being hired for at the AI × semiconductor-supply-chain intersection:
- Demand & allocation forecasting in production
- Multi-tier supplier risk & disruption monitoring
- Document AI over datasheets, PCNs, contracts, and regulations
- Supply-chain copilots & agents (control-tower automation)
- Export-control-aware AI (compliance as a first-class requirement)
- Time-series + LLM hybrid systems

### 🚀 Projects
- 🟢 **Domain Map** — one-page diagram of the semiconductor supply chain (fab →
  OSAT → distributor → OEM), labeled with the data each stage emits.
- 🟡 **Opportunity Memo** — pick 3 supply-chain pain points; write which AI
  technique fits each and why (with a rough data/feasibility note).
- 🔴 **Landscape Teardown** — analyze a real chip-shortage event (e.g. 2020–2023
  auto MCU crisis); map where an AI system could have given early warning.

---

## 🗺️ PHASE 1 - Programming Foundation (Python)

Python is the language of both AI and supply-chain data plumbing.

### What to Learn
- Core Python: types, control flow, functions, comprehensions, error handling
- Data stack: `pandas`, `numpy`, `polars` for large tabular supply-chain data
- File & interchange formats: CSV/Parquet, JSON, **EDI (X12 830/862/856)**, Excel
- **Async/await** — concurrent pulls from ERP, logistics, and pricing APIs
- HTTP clients (`httpx`), retries, rate limits, pagination
- Clean code: typing, modules, `pytest`, virtual envs, `uv`/`poetry`

### 🏭 Niche Focus
Parsing and normalizing supply-chain data: bills of materials (BOMs), purchase
orders, ASNs (advance ship notices), and EDI forecast/release documents into
tidy DataFrames.

### 🚀 Projects
- 🟢 **BOM Normalizer** — read messy multi-format BOMs (CSV/Excel) into a clean,
  validated schema with part-number canonicalization.
- 🟡 **EDI Parser** — parse X12 830 (planning) / 856 (ASN) files into structured
  records with unit tests.
- 🔴 **Async Ingest Service** — concurrently pull PO, inventory, and shipment data
  from 3 mock APIs, reconcile, and emit a unified daily snapshot.

---

## 🗺️ PHASE 2 - Mathematics & Statistics for AI

The math that powers forecasting, optimization, and risk.

### What to Learn
- Linear algebra: vectors, matrices, embeddings intuition
- Calculus: gradients & optimization intuition (for DL later)
- Probability & statistics: distributions, confidence intervals, hypothesis tests
- Time-series stats: stationarity, seasonality, autocorrelation
- **Optimization**: linear & integer programming for allocation and routing
- Metrics: MAE/MAPE/RMSE, bias, service level, fill rate

### 🏭 Niche Focus
Model allocation as a constrained optimization problem (limited fab capacity,
many demanding customers) and lead-time variability as a probability distribution.

### 🚀 Projects
- 🟢 **Forecast Error Toolkit** — implement MAE/MAPE/RMSE/bias and evaluate a
  naive forecast on real-ish demand data.
- 🟡 **Allocation LP** — use `PuLP`/`OR-Tools` to allocate scarce wafer capacity
  across customers to maximize weighted service level.
- 🔴 **Safety-Stock Optimizer** — compute safety stock under stochastic lead time
  and demand; visualize the cost-vs-service-level frontier.

---

## 🗺️ PHASE 3 - Machine Learning Fundamentals

Classical ML is still the workhorse of supply-chain forecasting.

### What to Learn
- Supervised learning: regression & classification
- Feature engineering for tabular & time-series data
- Tree ensembles: Random Forest, **XGBoost/LightGBM** (industry default)
- Time-series forecasting: ARIMA, Prophet, gradient-boosted lag models
- Model evaluation: cross-validation, backtesting, leakage avoidance
- `scikit-learn`, `statsmodels`, feature stores basics

### 🏭 Niche Focus
Demand forecasting, **lead-time prediction**, and supplier-defect / anomaly
detection — the three highest-ROI classical-ML tasks in chip supply chains.

### 🚀 Projects
- 🟢 **Lead-Time Predictor** — regress historical PO → receipt lead times on
  supplier, part family, and quarter.
- 🟡 **SKU Demand Forecaster** — LightGBM lag-feature model with seasonality and
  backtesting across multiple part numbers.
- 🔴 **Shortage-Risk Classifier** — predict which parts will go on allocation next
  quarter from lead-time trend, single-source flags, and demand slope.

---

## 🗺️ PHASE 4 - Deep Learning

When tabular models plateau, deep nets capture complex temporal and network
structure.

### What to Learn
- Neural net fundamentals: layers, activations, loss, backprop, regularization
- `PyTorch` (primary) and training loops
- Sequence models: RNN/LSTM → **Temporal Fusion Transformer (TFT)**, DeepAR, N-BEATS
- **Graph Neural Networks (GNNs)** for multi-tier supplier networks
- Embeddings for high-cardinality entities (parts, suppliers, sites)

### 🏭 Niche Focus
Two big wins: probabilistic **time-series nets** for demand/lead time, and
**GNNs over the supply graph** to propagate risk from a Tier-3 material supplier
up to your finished chip.

### 🚀 Projects
- 🟢 **LSTM Demand Model** — forecast a multi-series demand dataset; compare to
  the Phase 3 LightGBM baseline.
- 🟡 **Probabilistic Forecaster** — train a TFT/DeepAR model producing prediction
  intervals (P10/P50/P90) for planning.
- 🔴 **Supply-Graph GNN** — build a supplier→part→product graph; predict
  disruption-propagation risk with a GNN.

---

## 🗺️ PHASE 5 - Natural Language Processing & Transformers

Most supply-chain signal is trapped in unstructured text.

### What to Learn
- Text preprocessing, tokenization, embeddings
- Transformer architecture: attention, encoders/decoders (deep dive)
- Named-entity recognition, classification, semantic similarity
- `HuggingFace transformers`, sentence-transformers
- Document parsing: PDF/scan extraction, tables, layout

### 🏭 Niche Focus
Extract structured facts from supplier **contracts, PCNs (product change
notices), EOL notices, datasheets**, and disruption news — the raw material for
downstream RAG and agents.

### 🚀 Projects
- 🟢 **PCN Classifier** — classify supplier notices (EOL, cross, minor change) and
  extract affected part numbers.
- 🟡 **Datasheet Extractor** — pull key parameters (package, temp grade, MOQ, lead
  time) from datasheet PDFs into structured JSON.
- 🔴 **Disruption News NER** — entity + event extraction over news (supplier, site,
  hazard, impacted parts) feeding an early-warning feed.

---

## 🗺️ PHASE 6 - Large Language Models & AI Engineering

The core toolkit: driving LLM APIs reliably in production.

### What to Learn
- LLM APIs across providers: **Anthropic (Claude)**, OpenAI, Google (Gemini),
  Mistral, Groq, NVIDIA NIM
- Prompt engineering: structured outputs, JSON mode, tool/function calling
- Long context, system prompts, few-shot, guardrails
- Token/cost management, latency, retries, streaming
- Structured extraction with schemas (Pydantic, tool use)
- Evaluation: golden sets, LLM-as-judge, regression tests

### 🏭 Niche Focus
Build the "understanding" layer of a supply-chain copilot: turn a planner's
question or a pile of supplier emails into structured, actionable data — safely
and cheaply.

### 🚀 Projects
- 🟢 **Supplier-Email Triage** — classify & summarize inbound supplier emails
  (shortage, price change, ship confirmation) with structured output.
- 🟡 **Doc-to-JSON Extractor** — production-grade extraction of PO/ASN/datasheet
  fields with schema validation and eval harness.
- 🔴 **Planner Copilot v1** — natural-language Q&A over a structured supply-chain
  dataset via tool calling, with cost tracking and guardrails.

---

## 🗺️ PHASE 7 - Multi-LLM Orchestration

Different supply-chain tasks need different models; orchestration makes it
reliable and affordable.

### What to Learn
- Routing: pick model by task, cost, latency, and sensitivity
- Fallbacks & retries across providers; circuit breakers
- Orchestration frameworks: **LangGraph**, LangChain, CrewAI, AutoGen
- **Model Context Protocol (MCP)** for tool/data access
- Caching, batching, and cost-optimization patterns
- Observability: tracing multi-step LLM pipelines

### 🏭 Niche Focus
Route intelligently: a cheap fast model summarizes shipment updates, a strong
model reasons over allocation trade-offs, and a **compliance-checking step never
leaves an approved model / region** (export-control-aware routing).

### 🚀 Projects
- 🟢 **Task Router** — route supply-chain prompts to the cheapest capable model
  with a fallback chain and cost logging.
- 🟡 **Compliance-Aware Router** — enforce that export-control-sensitive prompts
  only hit approved, region-locked models; log the decision trail.
- 🔴 **Orchestrated Pipeline** — LangGraph pipeline: ingest → extract → assess →
  summarize, with retries, caching, and full tracing.

---

## 🗺️ PHASE 8 - RAG & Vector Databases

Ground LLMs in your suppliers, parts, and the regulations that govern them.

### What to Learn
- Embeddings, chunking strategies, metadata filtering
- Vector DBs: **pgvector**, Pinecone, Qdrant, Weaviate
- Retrieval quality: hybrid (BM25 + vector), reranking, HyDE, MMR
- Contextual compression, citations, and grounding
- Evaluation: retrieval precision/recall, faithfulness

### 🏭 Niche Focus
Two knowledge bases every chip supply chain needs: a **supplier/part knowledge
base** (datasheets, PCNs, contracts, quality records) and a **regulatory KB**
(export-control rules, entity lists) — both with citations planners can trust.

### 🚀 Projects
- 🟢 **Datasheet Q&A** — RAG over a folder of datasheets answering parametric
  questions with source citations.
- 🟡 **Export-Control Assistant** — cited answers over EAR/entity-list documents;
  explicitly flags uncertainty and defers to compliance.
- 🔴 **Supplier Knowledge Base** — multi-tenant hybrid-search KB over
  datasheets/PCNs/contracts with reranking and eval dashboard.

---

## 🗺️ PHASE 9 - AI Agents & Agentic Systems

Move from answering questions to taking (supervised) action.

### What to Learn
- Agent loops: reasoning, tool use, memory, reflection
- Multi-agent patterns: planner/worker, supervisor, debate
- Tool design & safety: human-in-the-loop, approvals, sandboxing
- LangGraph / CrewAI / AutoGen for agent workflows
- MCP servers exposing supply-chain tools & data

### 🏭 Niche Focus
The **control-tower agent**: continuously monitor signals (news, lead-time drift,
supplier health), assess impact against your BOMs, and recommend actions
(reroute, expedite, re-buffer) — with a human approving anything consequential.

### 🚀 Projects
- 🟢 **Disruption Alert Agent** — watch a news/RSS feed, match events to your part
  list, and post ranked alerts.
- 🟡 **Procurement Prep Agent** — assemble a supplier negotiation brief (spend,
  alternates, lead-time history, risk) on demand.
- 🔴 **Control-Tower Multi-Agent** — monitor → assess → recommend pipeline with
  specialized agents and a human-approval gate for actions.

---

## 🗺️ PHASE 10 - Fine-Tuning & Model Customization

When prompting isn't enough, adapt models to semiconductor language.

### What to Learn
- When to fine-tune vs. RAG vs. prompt (decision framework)
- PEFT: **LoRA, QLoRA**; instruction tuning; preference tuning (DPO)
- Dataset construction, cleaning, and eval design
- `HuggingFace PEFT`, `trl`, Axolotl; tracking with W&B
- Serving adapters efficiently

### 🏭 Niche Focus
Fine-tune a small model on **semiconductor terminology and document types**
(PCNs, datasheets, allocation letters) so extraction/classification is cheaper
and more accurate than a general model.

### 🚀 Projects
- 🟢 **LoRA Classifier** — fine-tune a small model to classify supplier-document
  types; beat the zero-shot baseline.
- 🟡 **Domain Extractor** — QLoRA-tune for structured extraction from datasheets;
  measure gains vs. prompting.
- 🔴 **Preference-Tuned Copilot** — DPO-tune responses toward planner-preferred,
  compliance-safe answers with a held-out eval.

---

## 🗺️ PHASE 11 - Generative AI (Beyond Text)

Generative techniques for scenarios, documents, and multimodal data.

### What to Learn
- Diffusion & image models (conceptual + API use)
- Multimodal models: vision + text (document & image understanding)
- Synthetic data generation and its pitfalls
- Speech/voice basics for hands-free planning tools

### 🏭 Niche Focus
**Synthetic scenario generation** to stress-test plans ("what if ABF substrate
lead times double?") and **multimodal document/image understanding** for scanned
datasheets, label photos, and fab-floor imagery.

### 🚀 Projects
- 🟢 **Scenario Generator** — generate plausible disruption scenarios with
  parameters for planners to war-game.
- 🟡 **Multimodal Datasheet Reader** — extract specs from scanned/image datasheets
  using a vision-language model.
- 🔴 **Synthetic Data Pipeline** — generate & validate synthetic demand/disruption
  data to augment scarce training sets, with leakage checks.

---

## 🗺️ PHASE 12 - MLOps, LLMOps & Production Systems

Ship it, monitor it, keep it honest.

### What to Learn
- Packaging: Docker; APIs with **FastAPI**
- Orchestration: Kubernetes basics, jobs & cron for batch forecasts
- CI/CD, model & data versioning (DVC, MLflow)
- Monitoring: data & concept **drift**, forecast-accuracy tracking
- LLMOps: tracing/eval (Langfuse, Helicone), prompt versioning
- Feature stores, retraining triggers, alerting

### 🏭 Niche Focus
Production forecasting pipelines that run every night, detect when demand
patterns **drift** (new product ramps, shortage shocks), and alert planners
before accuracy silently degrades.

### 🚀 Projects
- 🟢 **Forecast API** — serve the Phase 3/4 model via FastAPI + Docker with
  input validation.
- 🟡 **Nightly Pipeline** — containerized batch job: pull data → forecast → write
  results → publish accuracy metrics.
- 🔴 **Monitored LLM Service** — deploy the copilot with drift/accuracy dashboards,
  LLM tracing, and automated alerts.

---

## 🗺️ PHASE 13 - AI System Design

Architect the whole thing — interview-ready and real.

### What to Learn
- Requirements, constraints, SLAs for AI systems
- Data architecture: lakehouse, streaming vs. batch, feature stores
- Retrieval, caching, and cost/latency trade-offs at scale
- Reliability: fallbacks, graceful degradation, human-in-the-loop
- Security, multi-tenancy, and **data residency** by design

### 🏭 Niche Focus
Design a **Semiconductor Supply-Chain Control Tower**: ingestion of ERP + EDI +
news, a forecasting service, a RAG knowledge layer, agentic monitoring, and a
compliance boundary — all with clear data-residency zones.

### 🚀 Projects
- 🟢 **Design One-Pager** — architecture diagram + data flow for a disruption-alert
  system.
- 🟡 **Trade-Off Doc** — design a real-time supplier-risk service; justify
  batch-vs-stream, model, and storage choices.
- 🔴 **Control-Tower Architecture** — full design doc (components, data model,
  failure modes, compliance zones, scaling) for the capstone.

---

## 🗺️ PHASE 14 - SQL & Databases for AI Engineers

Supply-chain data lives in databases; you must speak their language.

### What to Learn
- SQL: joins, window functions, CTEs, aggregations
- Data modeling: star schemas for supply-chain facts (orders, shipments, inventory)
- **PostgreSQL + pgvector** for hybrid structured + semantic queries
- Redis for caching; warehouse basics (BigQuery/Snowflake)
- Query performance & indexing

### 🏭 Niche Focus
Model a supply-chain warehouse (parts, suppliers, POs, receipts, inventory,
shipments) and use **pgvector** so a copilot can join hard numbers with semantic
search over supplier documents in one place.

### 🚀 Projects
- 🟢 **Supply-Chain Schema** — design & load a normalized schema; write analytics
  queries (on-time %, lead-time by supplier).
- 🟡 **Text-to-SQL Assistant** — LLM that answers planner questions by generating
  safe, validated SQL against the schema.
- 🔴 **Hybrid Query Engine** — combine pgvector semantic search + SQL aggregates to
  answer questions like "risky single-source parts trending late."

---

## 🗺️ PHASE 15 - Quantization, Optimization & Efficiency

Make models cheap and deployable — including at the edge.

### What to Learn
- Quantization: GPTQ, AWQ, **GGUF**; INT8/INT4 trade-offs
- Efficient serving: **vLLM**, TGI, batching, KV-cache
- Small Language Models (SLMs) for cost-sensitive tasks
- Distillation; latency/throughput tuning
- Edge/on-prem inference constraints

### 🏭 Niche Focus
Run models **on-prem or at the edge** where fab and supplier data can't leave the
building — quantized SLMs for document classification on a fab-floor server or
near IoT sensor streams.

### 🚀 Projects
- 🟢 **Quantize & Serve** — quantize a model to GGUF and serve it locally; measure
  latency vs. accuracy.
- 🟡 **SLM Extractor** — deploy a small quantized model for document classification
  under a fixed latency/cost budget.
- 🔴 **On-Prem Inference Stack** — vLLM-served, air-gapped-style deployment with
  throughput benchmarks for sensitive supplier data.

---

## 🗺️ PHASE 16 - Reinforcement Learning for AI Engineers

Sequential decisions — inventory, buffering, routing — are RL's home turf.

### What to Learn
- RL fundamentals: MDPs, reward, policy, value functions
- Algorithms: Q-learning, DQN, PPO (conceptual + applied)
- RLHF/DPO for aligning LLM behavior
- Simulation environments for policy training
- Offline RL and safety constraints

### 🏭 Niche Focus
Frame **inventory & safety-stock policy** and **dynamic logistics routing** as RL
problems, trained in a supply-chain simulator before anything touches reality.

### 🚀 Projects
- 🟢 **Inventory Gym** — build a simple (s, S) inventory environment; train a
  tabular/DQN agent and compare to a heuristic.
- 🟡 **Buffering Policy** — RL agent that sets safety stock under stochastic
  lead time; evaluate cost vs. service level.
- 🔴 **Routing Optimizer** — RL/optimization hybrid for expedite-vs-standard
  shipping decisions under disruption, tested in simulation.

---

## 🗺️ PHASE 17 - AI Ethics, Safety & Governance

In this domain, governance isn't optional — it's law.

### What to Learn
- AI safety: hallucination control, guardrails, evaluation
- Bias & fairness in supplier scoring and allocation
- Data governance, privacy, and **data sovereignty**
- **Export controls (EAR/ITAR), entity lists, CHIPS Act** awareness
- Auditability, human oversight, and decision logging

### 🏭 Niche Focus
Make compliance a **first-class system feature**: export-control-aware data flows,
audit trails on every AI recommendation, fair and explainable supplier scoring,
and clear human accountability for consequential actions.

### 🚀 Projects
- 🟢 **Guardrail Suite** — add refusal/uncertainty guardrails and a compliance
  disclaimer layer to the copilot.
- 🟡 **Supplier-Scoring Audit** — audit a supplier-risk model for bias; document
  fairness and explainability findings.
- 🔴 **Governance Framework** — end-to-end policy for the capstone: data residency,
  export-control checks, audit logging, and human-in-the-loop approvals.

---

## 🗺️ CAPSTONE - Semiconductor Supply-Chain Control Tower

Bring every phase together into one production-grade platform.

### What You Build
An AI **control tower** that watches the supply chain, predicts trouble, and
helps planners act — safely and compliantly.

**Core capabilities:**
1. **Ingestion** — ERP/EDI + inventory + shipment feeds + external news/signals
2. **Forecasting service** — probabilistic demand & lead-time predictions with
   drift monitoring (Phases 3–4, 12)
3. **Risk engine** — multi-tier supplier & disruption risk, GNN-propagated
   (Phases 4, 9)
4. **Knowledge layer** — RAG over supplier docs + export-control regulations
   (Phase 8)
5. **Agentic monitoring** — control-tower agents: monitor → assess → recommend,
   with human approval (Phase 9)
6. **Copilot UI** — natural-language Q&A over data + documents (Phases 6, 14)
7. **Compliance boundary** — export-control-aware routing, audit logs, data
   residency (Phases 7, 17)

**Stack:** Python · FastAPI · PostgreSQL + pgvector · a vector DB · LangGraph ·
multi-LLM (Claude + others) · Docker/K8s · Langfuse · a forecasting model service.

**Deliverables:** running system + architecture doc + governance framework +
demo showing an end-to-end disruption caught, assessed, and mitigated.

---

## 📚 Resources Reference

**AI / ML**
- Hugging Face course & docs · PyTorch tutorials · `scikit-learn` user guide
- Anthropic, OpenAI, Google, Mistral API docs · LangGraph & LangChain docs
- `pgvector`, Qdrant, Pinecone docs · vLLM docs

**Forecasting & Optimization**
- `statsmodels`, Prophet, Nixtla (statsforecast/neuralforecast) docs
- Google OR-Tools · PuLP · Temporal Fusion Transformer / DeepAR papers

**Domain — Semiconductor Supply Chain**
- SEMI.org standards & market data · SIA (Semiconductor Industry Association)
- BIS export-administration regulations (EAR) & entity list · CHIPS Act primers
- EDI X12 (830/862/856) references · APICS/ASCM supply-chain fundamentals
- Industry analysis: TechInsights, SemiAnalysis, DigiTimes (for shortage signals)

> ⚠️ Treat all regulatory content as reference only — verify export-control and
> compliance decisions with qualified legal/trade counsel.

---

## 🎯 Skills Summary (Semiconductor Supply-Chain AI)

### Tier 1 — Must Have
- Python (async, pandas/polars, clean code)
- Time-series & tabular ML (LightGBM, forecasting, backtesting)
- LLM APIs + prompt engineering + structured extraction
- RAG fundamentals (pgvector, chunking, citations)
- SQL + data modeling for supply-chain facts
- FastAPI · Docker · Git/CI
- Supply-chain literacy (BOMs, lead time, allocation, EDI)

### Tier 2 — Highly Valued
- Multi-LLM orchestration (routing, fallbacks, cost control)
- LangGraph agents & MCP
- Probabilistic forecasting (TFT/DeepAR) & GNNs
- LLMOps (Langfuse) + drift monitoring
- Optimization (OR-Tools) for allocation/routing
- Vector DBs & hybrid search + reranking

### Tier 3 — Expert Level
- Fine-tuning (LoRA/QLoRA/DPO) on domain data
- Control-tower system design at scale
- RL for inventory/routing policy
- On-prem/edge quantized deployment
- Export-control-aware architecture & governance
- Multi-tier supply-graph risk modeling

---

## 🛤️ Learning Paths by Goal

### Path A: Forecasting & Planning Engineer
```
Phase 0 → 1 → 2 → 3 → 4 → 12 → 14 → Capstone
Focus: demand/lead-time forecasting in production
Timeline: 6-9 months
```

### Path B: Supply-Chain LLM / Copilot Engineer
```
Phase 0 → 1 → 6 → 7 → 8 → 9 → 12 → 13 → Capstone
Focus: copilots, RAG, agents over supply-chain data
Timeline: 6-9 months
```

### Path C: Risk & Compliance AI Engineer
```
Phase 0 → 1 → 3 → 5 → 8 → 9 → 17 → Capstone
Focus: disruption monitoring, supplier risk, export-control-aware AI
Timeline: 6-9 months
```

### Path D: Full Control-Tower Architect
```
All Phases → All Projects → Capstone
Focus: the complete Semiconductor Supply-Chain Control Tower
Timeline: 12-18 months
```

---

## 🏆 Portfolio Projects (Ship These)

1. **Lead-Time & Demand Forecaster** — probabilistic forecasts with drift
   monitoring, served via API.
2. **Disruption Early-Warning System** — news + signal monitoring mapped to your
   BOM, with ranked alerts.
3. **Supplier Knowledge Base (RAG)** — hybrid search over datasheets, PCNs, and
   contracts with citations.
4. **Export-Control Compliance Assistant** — cited, uncertainty-aware Q&A over
   trade regulations.
5. **Multi-Tier Supply-Graph Risk Model** — GNN propagating risk from raw
   materials to finished chips.
6. **Text-to-SQL Planner Copilot** — natural-language analytics over a
   supply-chain warehouse.
7. **Capstone: Semiconductor Supply-Chain Control Tower** — the full production
   platform.

---

*Last Updated: 2026 | Semiconductor Supply Chain & Logistics Edition*
*"In chips, the shortage isn't the surprise — the surprise is not seeing it coming."*
