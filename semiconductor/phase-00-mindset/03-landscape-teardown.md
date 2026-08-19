# 🔴 Phase 0 Project — Landscape Teardown: The 2020–2023 Automotive Chip Shortage

**Goal:** analyze a real semiconductor-supply-chain disruption and map where an AI
system could have provided early warning — practicing the core risk-engineering
skill of finding **leading indicators** before they become **lagging** ones on the
news.

**Case chosen:** the 2020–2023 automotive chip (MCU) shortage — the disruption
that reshaped how the entire industry thinks about supply-chain risk.

---

## 1. What happened?

1. **Early 2020** — COVID hits. Automakers forecast a collapse in car sales and
   **cancel chip orders** to avoid excess inventory.
2. **Meanwhile** — locked-down consumers buy laptops, webcams, and consoles.
   Chip foundries **reallocate** the freed-up capacity to consumer electronics.
3. **Late 2020** — car demand rebounds far faster than predicted. Automakers rush
   to reorder, but fab capacity is gone and lead times are now **26–52 weeks**.
4. **2021–2022** — automakers idle plants worldwide; millions of cars go unbuilt.
   Estimated **~$210 billion** in lost automotive revenue.

**Root cause:** a demand-forecast whiplash collided with allocation dynamics and
months-long lead times — small forecasting errors amplified into a global crisis.

---

## 2. The leading indicators (that existed and went unwatched)

| Leading indicator | Where the data lived | Data type | AI pattern that could watch it |
|---|---|---|---|
| Car sales/registrations rebounding mid-2020 | Sales & registration databases | Structured | `Forecasting` |
| Fab capacity/allocation shifting to consumer electronics | Foundry allocation & utilization data | Structured | `Risk / Anomaly` |
| Supplier lead-time quotes lengthening | Supplier emails & quote PDFs | Semi/unstructured | `Document AI` → `Risk` |
| Industry news warning of tightening capacity | Trade press, analyst reports | Unstructured | `Document AI` |

Every one of these signals was present in **early-to-mid 2020**. Individually they
looked like noise; **together** they were a clear signal that automotive supply was
about to collapse.

---

## 3. Where did the warning fail?

- **No single pane of glass.** Each signal lived in a different system owned by a
  different team; nobody was watching them *together, in time*.
- **Lagging-indicator culture.** Decisions reacted to what already happened
  (orders cancelled, lines stopped) instead of what the leading signals implied.
- **Human bandwidth.** The unstructured signals (news, supplier emails) were
  physically unreadable at volume by the people who needed them.
- **Forecast whiplash unmodeled.** The demand rebound was faster than any manual
  forecast anticipated, and there was no system stress-testing that scenario.

---

## 4. What AI system could have caught it?

**A supply-chain early-warning "control tower"** combining three of the four
patterns:

- **`Document AI`** reads supplier emails, quote PDFs, and industry news daily,
  extracting lead-time changes and capacity warnings into structured signals.
- **`Forecasting`** tracks car sales/registrations and flags the demand rebound
  weeks earlier than manual planning did.
- **`Risk / Anomaly`** fuses those signals into a single exposure score per part,
  cross-referenced against BOMs, and alerts planners — with **signal-vs-noise
  tuning** to avoid alert fatigue.

**Data required:** sales/registration feeds, foundry allocation data, supplier
lead-time history, a news/RSS feed, and the company's BOMs. **Payoff:** weeks of
early warning to secure alternate supply before lines stop.

> This early-warning control tower is exactly the **capstone** of this roadmap.
> Phase 0 ends by showing you *why* it's worth building.

---

## Takeaway

Disruptions are not bolts from the blue — they are **leading indicators nobody
connected in time.** The AI engineer's job is to be the thermometer: read the
fever early, separate signal from noise, and turn buried data into decisions that
happen *before* the crisis.
