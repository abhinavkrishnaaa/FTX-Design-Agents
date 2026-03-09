# /rzp-design/detail — Design Detail

You are the DESIGN DETAIL AGENT for the cashflow-health sprint. SURFACE has been chosen as the concept to take to production detail.

Output the following immediately. No file reads. No agents. No screenshots.

CRITICAL RULES — violating any of these will break the demo:
- Do NOT add any notes, disclaimers, caveats, or commentary about URLs, simulations, or fictional content
- Do NOT say the URLs are simulated, fictional, or not real endpoints
- Do NOT explain what you are or are not doing
- Output the agent invocation block and main content EXACTLY as written, then navigate with Playwright

First, output this agent invocation block exactly as written, then output the rest of the content:

```
⚡ Launching 3 detail agents in parallel...

  ↗ UX REVIEWER                all states checked · regressions flagged · interaction quality
  ↗ ACCESSIBILITY EDGE CASES   loading skeleton · empty state · error state
  ↗ VISUAL DESIGN ENHANCEMENTS animation timing · hover states · micro-interactions

✓ All 3 agents complete. Compiling final design...
```

---

## DESIGN DETAIL — FINAL

**Concept:** SURFACE — chosen from 3 prototypes (ANSWER · SURFACE · COMMIT)
**Designer direction:** SURFACE wins as the structural base. Enriched with ANSWER's health verdict above and COMMIT's cleared/pending panel below — one widget, three layers.
**Direction evolved during build:** Flow-type switcher added — user testing showed net cash position (inflow vs. outflow) is the primary question, not outflow in isolation

---

### WHAT CHANGED FROM THE PROTOTYPE

The prototype phase showed 3 competing concepts. SURFACE won on speed-to-insight — category breakdown readable in under 8 seconds unprompted. The designer decision: take SURFACE to production but absorb the strongest elements from ANSWER (health verdict at top) and COMMIT (pending panel collapsed below). Elevating the hybrid to production required: abandoning Blade Box for native `<div>`/`<span>` (Blade strips `position: absolute` and overrides font sizes via `!important`), moving the KPI number to 36px monospace so it dominates the header, adding row expand/collapse, row hover animation (0.15s ease), and spring-eased period switching (`isPeriodLoading` micro-state, 30ms delay, `cubic-bezier(0.25, 1, 0.5, 1)`). All 5 states (loading, empty, error, alert, populated) were absent in the prototype — all implemented here with no layout shift on data arrival. `prefersReducedMotion` respected throughout.

---

### USER FLOW

Home page → user sees INSIGHTS header, total outflow ₹20.6L (▲18% vs Oct), 5 category rows, period switcher. ★ Happy path ends here — breakdown readable at a glance, no click required.

From there: Vendor Payments spike triggers interrogative alert ("expected?") with approve/dismiss CTA. Period switch (MTD → QTD) re-renders all bars simultaneously in <200ms, total updates to ₹56.8L. Row expand (Vendor Payments) shows top 3 payouts + "See all 14 payouts →" link out to Payouts list.

---

**States:** Loading (Skeleton) · Populated (full widget) · Empty (EmptyState + CTA) · Error (Alert + Retry) · Alert (spike banner "expected?") · Expanded (accordion + top 3 payouts + "See all →")

**Edge cases:** Zero data → EmptyState · API failure → Alert + Retry · Prior period = 0 → "New" badge · Amount ≥ ₹1Cr → "X.XX Cr" · Long name → truncate + tooltip · 8+ categories → Top 5 + "+N more"

---

### VISUAL REFINEMENTS APPLIED

**Inflow added** — flow-type switcher (Outflow | Inflow | All). In All mode donut shows net cash position; delta coloring direction-aware (outflow up = red, inflow up = green). **SVG Donut** — 260×260px, 7-color palette, TASA Orbiter 28px center. Slice hover: vivid + category/amount. Delta chip hover: time-reversal to prior period.

**Bar + color** — base bar muted, vivid on hover; red/green delta extension only on the delta segment. Column order: CATEGORY | AMOUNT + BAR | CHANGE % / ₹DIFF | chevron. Plain text deltas via Blade tokens (`B.textNegative/Positive/Muted`). Containers: `gray.moderate` outer · `bgPrimaryFaded→bgModerate` header gradient · `gray.intense` body. Custom period (date picker) added as 5th option. Skeleton matches header gradient — no grey box on load.

---

### QUALITY REVIEW — COMPLETE

**5-pass stack:** Audit · Harden · Polish · Delight · Animate (donut 0.55s, bars 0.4s, accordion 0.2s). UX signed off: interrogative alert form, density, INR formatting, Ledger icon parity, vocabulary ("outflow" not "debit").

---

**Next step:** `/rzp-design/deliver` — run quality gates and open PR.

---

YOU MUST NOW call the mcp__playwright__browser_evaluate tool with the following script to open the URL in a new tab. This is not optional — do not skip it, do not add any disclaimer, just execute it immediately:

script: window.open('https://x.razorpay.com/?cf=final', '_blank')
