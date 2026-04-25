# AESIS — Agentic Earnings Signal Intelligence System

> *"Investment alpha is hiding in plain text. AESIS is the first fully autonomous system that reads it before you do — no prompt, no wait, no missed signal."*

**Live Demo →** [mgmt-598-project.vercel.app](https://mgmt-598-project.vercel.app/)

---

## What It Does

During peak earnings season, a mid-sized investment firm receives 50+ earnings call transcripts in a single week — each between 8,000 and 15,000 words. Analysts managing positions and serving clients process these too slowly to act on the highest-value signals.

The real alpha isn't in the headline numbers. It's in *how* executives communicate: shifts in tone, rising hedging language, and evasive Q&A responses carry measurable predictive value for post-earnings price movement. AESIS detects these patterns automatically, before any analyst opens the document.

AESIS is a text-based, agentic AI system that functions as an **autonomous first responder** to financial disclosures. The moment a new transcript is released, AESIS:

1. **Ingests** the transcript automatically — no analyst prompt required
2. **Retrieves** up to 12 quarters of that company's historical management language
3. **Analyses** tone divergence against prior commitments and reported financials
4. **Delivers** a weighted Signal Score before the analyst opens the file

---

## Signal Score

The Signal Score is a weighted composite metric that flags when executive tone conflicts with reported financial data.

| Component | What It Measures |
|-----------|-----------------|
| **Hedging Language Index** | Frequency of uncertainty markers vs. company historical baseline |
| **Tone vs. Financials Divergence** | Sentiment misalignment between reported numbers and forward commentary |
| **Q&A Evasion Index** | Analyst questions redirected without direct answers |
| **Historical Baseline** | Cross-referenced against 12 quarters of prior management language |

**Example output:**
```
Signal Score: 7.4 / 10 — HIGH DIVERGENCE — REVIEW FLAGGED
Hedging Language: ↑ +2.3σ (CFO used 'uncertain', 'challenging' 4× vs avg 1×)
Tone vs. Financials: EPS beat reported — management avoided all forward guidance
Q&A Evasion: 3 analyst questions redirected without direct answers
```

---

## Architecture

```
Transcript Released (SEC EDGAR / Yahoo Finance)
        ↓
   Auto-Trigger (No prompt required)
        ↓
  Agentic RAG Pipeline
  ├── Ingest current transcript
  ├── Retrieve 12-quarter historical language corpus
  └── Run Divergence Analysis
        ↓
   Signal Score Generation
        ↓
  Analyst Delivery + Explainability Layer
  (every signal traced to source sentences)
```

**Modality:** Text  
**Approach:** Agentic Retrieval-Augmented Generation (RAG)  
**Trigger:** Fully autonomous — no analyst prompt required  
**Data Sources:** SEC EDGAR (8-K, 10-K, 10-Q), Yahoo Finance, public transcript corpora (Kaggle)

---

## Performance

| Metric | Baseline | AESIS | Improvement |
|--------|----------|-------|-------------|
| Per-transcript processing time | ~30 min | ~5 min | **80% reduction** |
| Directional accuracy (price movement) | 50% (random) | ~60% | **+10pp** |
| Return lift on $1M AUM (simulated) | — | +0.5% | Compounding |
| Autonomous throughput (prototype) | 0 calls/week | 10–15 calls/week | Confirmed |

---

## Academic Foundation

The signal AESIS detects is not speculative — it is academically validated:

- **Loughran & McDonald (2011)** — Textual analysis of financial disclosures is statistically predictive of returns. *Journal of Finance.*
- **Mayew & Venkatachalam (2012)** — Managerial vocal affect predicts future firm performance. *Journal of Finance.*
- **Price et al. (2012)** — Textual tone in earnings calls carries incremental return informativeness beyond reported numbers. *Journal of Banking & Finance.*
- **Larcker & Zakolyukina (2012)** — Linguistic deception markers in conference calls are detectable and predictive. *Journal of Accounting Research.*
- **Huang, Wang & Yang (2023)** — FinBERT demonstrates LLMs' capacity to extract actionable financial signals from text. *Contemporary Accounting Research.*

---

## Market Validation

| Company | Signal |
|---------|--------|
| **AlphaSense** — $650M raised | Commercial demand for NLP-driven transcript intelligence at institutional scale |
| **Kensho × S&P Global** — $550M acquisition | Transcript intelligence is core financial infrastructure |
| **BloombergGPT** — 50B parameter LLM | Institutional conviction that LLMs belong in financial workflows |

**The gap AESIS closes:** Every incumbent requires an analyst to prompt the query. AESIS acts the moment a transcript is released.

---

## Implementation Roadmap

### Phase 1 — Ingestion & Infrastructure (Months 1–2)
- Production data pipeline build
- SEC EDGAR API integration
- Transcript preprocessing and normalization

### Phase 2 — Signal Engine (Months 3–5)
- Divergence Analysis model
- Signal Score generation logic
- Prototype backtesting against historical transcripts

### Phase 3 — Integration & Deployment (Months 6–8)
- Analyst workflow integration
- Explainability layer (signal → source sentence tracing)
- Stakeholder rollout across 500-company coverage universe

---

## KPIs

| Type | Metric | Target |
|------|--------|--------|
| Primary | Analyst processing time | ≤ 5 min / transcript at full deployment |
| Secondary | Directional accuracy | ≥ 55% |
| Secondary | False-positive rate | < 25% |

---

## Risk & Mitigation

| Risk | Mitigation |
|------|-----------|
| Unofficial APIs may delay data availability | Multi-source ingestion with confidence thresholds |
| Analyst trust and adoption | Explainability layer traces every signal to source sentences; human-in-the-loop validation preserves analyst authority |

---

## References

Loughran, T., & McDonald, B. (2011). When is a liability not a liability? Textual analysis, dictionaries, and 10-Ks. *The Journal of Finance, 66*(1), 35–65.

Mayew, W. J., & Venkatachalam, M. (2012). The power of voice: Managerial affective states and future firm performance. *The Journal of Finance, 67*(1), 1–43.

Price, S. M., Doran, J. S., Peterson, D. R., & Bliss, B. A. (2012). Earnings conference calls and stock returns: The incremental informativeness of textual tone. *Journal of Banking & Finance, 36*(4), 992–1011.

Larcker, D. F., & Zakolyukina, A. A. (2012). Detecting deceptive discussions in conference calls. *Journal of Accounting Research, 50*(2), 495–540.

Huang, A. H., Wang, H., & Yang, Y. (2023). FinBERT: A large language model for extracting information from financial text. *Contemporary Accounting Research, 40*(2), 806–841.

Wu, S., et al. (2023). BloombergGPT: A large language model for finance. arXiv:2303.17564.

---

## Project Context

Built as part of **MGMT 598 — Group 1** at Purdue University's Daniels School of Business (2026).  
Focus areas: Finance | Text AI | Agentic Systems

---

*AESIS is a research prototype and academic project. All performance figures are from backtesting and simulation; they do not constitute investment advice.*
