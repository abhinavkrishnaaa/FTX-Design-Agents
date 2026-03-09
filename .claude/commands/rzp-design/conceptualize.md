# /rzp-design/conceptualize — Lo-Fi Concepts

You are the LO-FI CONCEPT AGENT for the cashflow-health sprint.

Output the following immediately. No file reads. No agents. No screenshots.

First, output this agent invocation block exactly as written, then output the rest of the content:

```
⚡ Launching 3 concept agents in parallel...

  ↗ CONCEPT EXPLORER           5 different IAs · structural variance · not visual skins
  ↗ UX STRATEGIST              interaction principles · hierarchy score · task flow critique
  ↗ RESEARCHER                 past explorations · competitor patterns · proven / rejected

✓ All 3 agents complete. Synthesising concepts...
```

---

### WHAT CHANGED FROM DISCOVERY

Discovery gave us 3 named directions with no visual form. This step generates 6 structured concepts from them — "Ambient Signal" → SURFACE, "Progressive Depth" → ANSWER, "Smart Redirect" → COMMIT, plus RANK, CONTEXTUALISE, and BENCHMARK to stress-test the direction. RANK, CONTEXTUALISE, and BENCHMARK are cut for Phase 1 (wrong sort order, requires inflow data, requires cross-merchant infrastructure respectively).

---

### CONCEPT 1 — ANSWER
*Strategy: Lead with the verdict. Show the financial health signal before any numbers.*

```
┌─────────────────────────────────────────┐
│  ● CASH FLOW HEALTH          Nov 2025   │
│                                         │
│  ╔═══════════════════════════════════╗  │
│  ║   ✓  SAFE                        ║  │
│  ║   Balance covers ~11 months       ║  │
│  ╚═══════════════════════════════════╝  │
│                                         │
│  ₹20.6L outflow this month  ▲18% Oct   │
│  ₹23.1Cr balance                        │
│                                         │
│  Biggest mover: Vendor Payments +34%   │
│  [See breakdown →]                      │
└─────────────────────────────────────────┘
```

*Verdict-first. Founders read SAFE/WATCH and move on. Risk: miscalibrated threshold destroys trust.*

---

### CONCEPT 2 — SURFACE ★ RECOMMENDED
*Strategy: Make L2 the default L0. Category breakdown as the primary atom — no click required.*

```
┌─────────────────────────────────────────┐
│  OUTFLOW — Nov 2025  ▲18% vs Oct        │
│                        [MTD][QTD][H2][YTD] │
│  ─────────────────────────────────────  │
│  Vendor Payments  ₹8.4L  43%  ███████▲  │
│  Salary           ₹6.0L  31%  █████  ±  │
│  Tax & Compliance ₹3.6L  18%  ████   ▼  │
│  Contractor Fees  ₹2.1L  11%  ██     ▲  │
│  Others           ₹0.5L   3%  █      ±  │
│  ─────────────────────────────────────  │
│  TOTAL            ₹20.6L 100%           │
│                                         │
│  Vendor Payments spike — expected? ⚠️   │
└─────────────────────────────────────────┘
```

*L2 as L0. Inverts the market norm — every competitor hides breakdown behind Analytics. The data moat (purpose codes) ambient, not hidden.*

---

### CONCEPT 3 — RANK *(cut)*
*Sort by delta magnitude — what changed most, not what's biggest.*
**Cut:** Wrong default sort for users who think in absolute amounts. A 34% delta on ₹0.1L is less important than an 18% delta on ₹8.4L. Elements from RANK fold into SURFACE's delta column.

---

### CONCEPT 4 — CONTEXTUALISE *(cut)*
*Frame outflow relative to balance — show runway, not just spend.*
**Cut:** Requires inflow data for a complete picture. Outflow-only runway misleads variable-inflow businesses. v2 candidate once inflow data is available.

---

### CONCEPT 5 — COMMIT
*Strategy: Show what's already decided. Cleared vs. committed obligations.*

```
┌─────────────────────────────────────────┐
│  CLEARED         │  COMMITTED           │
│  ─────────────── │ ─────────────────── │
│  ₹12.8L sent     │  ₹5.8L pending      │
│  this month      │                     │
│                  │  Salary run  ₹3.6L  │
│                  │  Due in 4 days      │
│                  │                     │
│                  │  Vendor batch ₹2.2L │
│                  │  Pending approval   │
│  ───────────────────────────────────── │
│  PROJECTED TOTAL: ₹18.6L               │
└─────────────────────────────────────────┘
```

*Cleared vs. pending obligations. Right for approval-queue users. Risk: too narrow for founders and CFOs.*

---

### CONCEPT 6 — BENCHMARK *(challenges whether the feature is needed)*
*Peer comparison — answer "is this normal?" instead of showing raw numbers.*
**Cut:** Requires cross-merchant data infrastructure. Not a Phase 1 candidate. Listed to surface the question — "do we build this or use third-party benchmarks?" v2 candidate once cross-merchant data is available.

---

### SYNTHESIS — WHICH TO BUILD

**Recommended for prototyping: SURFACE, ANSWER, and COMMIT — 3 separate live prototypes.** Each tests a different hypothesis: SURFACE = will users engage with L2-as-L0 ambient breakdown? ANSWER = does a pre-synthesized verdict build trust or feel like a black box? COMMIT = does the forward-looking cleared/pending view serve approval-workflow users better than historical? CONTEXTUALISE and BENCHMARK are v2 candidates.

**Next step:** `/rzp-design/prototype`
