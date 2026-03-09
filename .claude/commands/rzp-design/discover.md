# /rzp-design/discover — Discovery

You are the DISCOVERY AGENT for the cashflow-health sprint.

Output the following immediately. No file reads. No agents. No screenshots.

First, output this agent invocation block exactly as written, then output the rest of the content:

```
⚡ Launching 5 research agents in parallel...

  ↗ USER INSIGHTS              what changed · was it justified · is it repeatable
  ↗ PRODUCT CONTEXT            existing features · hidden capability · don't rebuild
  ↗ USAGE INSIGHTS             engagement signals · drop-off points · feature reach
  ↗ COMPETITOR RESEARCH        PayTM / Juspay · industry patterns · what works
  ↗ EXISTING PRODUCT           UI deep audit · disabled features · flag-level checks

✓ All 5 agents complete. Synthesising findings...
```

---

## DISCOVERY COMPLETE — cashflow-health

**5 agents ran in parallel.** Research synthesized across: competitor analysis · codebase scan · user interviews · usage data · existing product audit.

---

### THE PROBLEM IN ONE SENTENCE

Finance leaders at Indian mid-market companies land on the RazorpayX home page every day, but cannot tell whether their business is cash-flow positive this month without navigating away — despite the product already holding exactly the data they need.

---

### ANCHOR INSIGHT

> "RazorpayX captures payout purpose codes at the moment of transaction initiation — real-time, structured, categorized — and uses this data only for compliance reports. Every competitor in the Indian market sits on the same latent data moat and does nothing with it."

**This changes the design question from:** "How do we show cash flow health?"
**To:** "How do we surface what we already know, in the right place, at the right moment?"

---

### WHO IS AFFECTED

| Persona | Current behaviour | Frequency | Severity |
|---------|-------------------|-----------|----------|
| CFO / Head of Finance | Opens Tally → exports Excel → runs manual summary | Daily–Weekly | HIGH |
| Head of Finance (Operational) | Navigates to Payouts Insights, finds it too granular | Daily | HIGH |
| SME Founder | Checks RazorpayX when anxious — salary run, large vendor bill | Variable | MEDIUM |

---

### TOP 3 PAIN POINTS (ranked by severity × frequency)

**#1 — No cash flow signal at L0** *(4.8 / 5)*
Home page shows Activity Feed + payment success rate. Neither answers "are we cash-positive this month?" Users leave the product to answer a question the product could already answer.

**#2 — Navigation friction to the right data** *(4.2 / 5)*
Tally → Excel → manual summary: 30–60 minutes per check. Every data point needed for that summary exists in RazorpayX, queryable in milliseconds.

**#3 — No category attribution on home page** *(3.6 / 5)*
Payout purpose codes exist on every transaction. They're used only for compliance exports. No user sees them at L0 unless they navigate to Payouts Insights — which most don't.

---

### 3 PROPOSED DESIGN DIRECTIONS

**Direction 1 — Ambient Signal**
Always-visible widget showing outflow MTD + delta vs prior period with fiscal period tabs (MTD / QTD / H2 / YTD). Passes the 3-second test for every persona.

**Direction 2 — Progressive Depth**
Expandable widget: L0 = totals, L1 = category breakdown, L2 = top payouts per category, L3 = link to Payouts Insights. Every persona stops at their natural depth.

**Direction 3 — Smart Redirect**
Anomaly-detecting banner: only surfaces when something needs attention. Low friction, but dependent on threshold calibration — gets noisier before it gets smarter.

---

### DELIGHT OPPORTUNITIES IDENTIFIED

- **DO1** — Fiscal period label surfaced in plain language (e.g., "Q3 FY26: Oct – Dec 25") without navigation
- **DO2** — Balance runway in plain language ("~11 months at current run rate")
- **DO3** — Period switch re-renders all 5 category bars simultaneously in <200ms — viscerally satisfying vs. a Tally export
- **DO4** — Biggest mover callout visible at L0 without any click — pre-synthesized answer, not raw data

---

**Next step:** `/rzp-design/conceptualize` — generate 6 fundamentally different design concepts as working diagrams.
