# 🟡 Phase 0 Project — AI Opportunity Memo

**Goal:** practice the core skill of an AI engineer — spotting where AI creates
real value in the semiconductor supply chain, matching each opportunity to a
proven AI pattern, and sanity-checking whether the data to build it actually
exists.

**The four AI patterns** (every project is one of these):
`Forecasting` · `Risk / Anomaly` · `Document AI` · `Copilot / Agent`

**Feasibility rule:** an idea is only good if the data to power it exists. Each
opportunity below includes a data + difficulty note.

---

## Opportunity 1 — Product & supplier exposure questions

| Field | Detail |
|---|---|
| **Pain point** | Planners can't quickly answer "which of our products are exposed to Supplier X / a given part / Taiwan?" The answer is buried across ERP tables and takes hours to assemble by hand. |
| **AI pattern** | `Copilot / Agent` |
| **Why it fits** | A copilot understands a plain-English question and answers it by **retrieving from our own connected supply-chain data** (not from its training) — turning an hours-long lookup into a same-minute answer. |
| **Data needed** | BOMs (product → part mapping), supplier master data, part → supplier mapping, supplier site/geography. |
| **Difficulty** | **Medium** — the data usually exists in the ERP but is scattered; most of the work is connecting it cleanly. The AI retrieval + Q&A layer is well-established (RAG, Phase 8). |

---

## Opportunity 2 — Datasheet spec extraction

| Field | Detail |
|---|---|
| **Pain point** | Extracting specs (temperature grade, package type, MOQ, lead time) from hundreds of datasheet PDFs is slow, manual, and error-prone. |
| **AI pattern** | `Document AI` |
| **Why it fits** | Datasheets are unstructured documents; modern models can read them and output clean, structured fields — exactly the "unread data → usable data" win. |
| **Data needed** | The datasheet PDFs, a defined schema of fields to extract, and a few hand-checked examples to validate accuracy. |
| **Difficulty** | **Easy–Medium** — extraction is very doable; the real work is validating accuracy on messy or scanned PDFs. |

---

## Opportunity 3 — Allocation / shortage early warning

| Field | Detail |
|---|---|
| **Pain point** | There's no early warning before a part goes on allocation or into shortage — by the time it's obvious, it's a crisis with months-long lead times to recover. |
| **AI pattern** | `Risk / Anomaly` |
| **Why it fits** | A risk model scores each part's likelihood of going short, giving planners weeks of early warning to secure alternates before the line stops. |
| **Data needed** | Historical lead-time trends, single-source flags, order/backlog data, and **labeled past shortage events** to learn from (optionally external news signals). |
| **Difficulty** | **Hard** — predicting the future is inherently hard, signals are noisy, and labeled shortage history is scarce. Highest value, highest difficulty. |

---

## Takeaway

Two of these lean on **classical ML** (Opportunity 3 — risk/forecasting, learned
early in Phases 3–4) and two lean on **LLM skills** (Opportunities 1 & 2 —
copilots and document AI, learned in Phases 6–9). Notice the pattern: the easiest,
fastest wins are usually **Document AI**; the highest-value, hardest wins are
usually **Risk/Forecasting**. A good roadmap ships the easy wins first to build
credibility, then invests in the hard ones.
