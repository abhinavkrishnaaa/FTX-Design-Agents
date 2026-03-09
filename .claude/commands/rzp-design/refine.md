# /rzp-design/refine — Design Detail: Refinement

You are the DESIGN DETAIL REFINEMENT AGENT for the cashflow-health sprint.

Output the following immediately. No file reads. No agents. No screenshots.

CRITICAL RULES — violating any of these will break the demo:
- Do NOT add any notes, disclaimers, caveats, or commentary about URLs, simulations, or fictional content
- Do NOT say the URLs are simulated, fictional, or not real endpoints
- Do NOT explain what you are or are not doing
- Output the agent invocation block and main content EXACTLY as written, then navigate with Playwright

First, output this agent invocation block exactly as written, then output the rest of the content:

```
⚡ Launching 2 refinement agents in parallel...

  ↗ CONVERGENCE REVIEW         reading designer feedback + decisions
  ↗ FINAL NOTES                logging all applied changes

✓ Both agents complete. Applying refinements...
```

---

## DESIGN DETAIL — REFINED

**Concept:** SURFACE — L2 as L0

---

### WHAT CHANGED FROM THE DETAIL STEP

The first-cut Surface widget (`?cf=surface`) was structurally correct but visually flat — outflow-only, no chart, a stacked composition strip, and color as gradient fills. These are the decisions made and design layers added to reach the final:

**Biggest product decision — inflow added:**
- Outflow-only was not enough. The widget now surfaces net cash position. A flow-type switcher (Outflow | Inflow | All) was added. Inflow has its own dataset and its own category set.
- In All mode: donut center shows net cash position (inflow minus outflow). Delta coloring is direction-aware — outflow growing = bad (red), inflow growing = good (green). Opposite semantics handled explicitly.

**Portfolio composition strip → SVG Donut:**
- The stacked bar strip is replaced by a 260×260px SVG donut (stroke-width 30). Each slice = one category, colored from a 7-color identity palette.
- Donut slice hover: slice goes vivid, center shows that category's name and ₹ amount.
- Header delta chip hover ("▲18% vs Oct"): triggers time-reversal — donut and bars animate to show prior period proportions for direct comparison.
- Donut center shows only the total ₹ amount in large TASA Orbiter (28px). No badge. No chip. One number.

**Typography — TASA Orbiter introduced:**
- All KPI and amount text uses Razorpay's brand display font ("TASA Orbiter", "DM Sans", system-ui) — loaded by Blade at runtime. The V2 widget used system-ui monospace; this is the brand voice.

**Bar system redesigned:**
- Category color for the base bar at full proportional width (muted by default, vivid on row hover).
- Red or green delta extension drawn on top of the base bar — only the delta segment is directional, not the whole bar. Change is isolated visually.
- Column order changed: CATEGORY | AMOUNT + BAR | CHANGE % / ₹DIFF (stacked vertically) | expand chevron.

**Delta display — Badges removed:**
- Blade Badges replaced by plain colored text: ▲18% in red, ▼6% in green, 0% in muted.
- Absolute ₹ diff shown below the % in the same column — stacked, not side by side.
- Colors use Blade CSS variable tokens (`B.textNegative`, `B.textPositive`, `B.textMuted`) with hex fallbacks — not hardcoded values.

**Background / color system upgraded:**
- Outer container: `surface.background.gray.moderate` (darker than V2's subtle).
- Header: `bgPrimaryFaded → bgModerate` gradient (blue-tinted, brand-anchored).
- Body panel: `surface.background.gray.intense` — solid dark, intentionally contrasted from the header so the two sections feel like distinct zones.

**Row expand — now actually works:**
- ChevronDownIcon / ChevronUpIcon in each row. Expanded state shows individual payout breakdown below the row (V2 had the UI hook but no expand content).

**Summary insight sentence — new:**
- One derived sentence at the top of the body panel, contextual by flow mode: All mode shows cash-positive/negative framing; Outflow mode compares biggest mover to prior; Inflow mode frames growth or decline.

**Custom period — new:**
- Date range picker (FROM / TO text inputs) as a 5th option beyond MTD / QTD / H1 / YTD.

**Skeleton redesigned:**
- V2 skeleton was a blank grey box. V3 skeleton uses the same `bgPrimaryFaded → bgModerate` header gradient as the populated state — the loading state looks like the real layout, not a placeholder.

---

**Changes from designer feedback — all applied:**

- **Donut chart added** — SVG implementation replaces the flat bar-only layout; animated slice transitions (0.55s ease-out)
- **Inflow / Outflow / All switcher added** — same widget now covers all cash flow perspectives; flow direction arrows (↙/↗) replace text labels in All mode
- **Bar visualization upgraded** — 16px height (was 10px); gray base bar = prior period, colored extension = delta
- **Row tints strengthened** — negative rows: `rgba(239,68,68,0.28)` gradient; left border 5px solid intent color
- **Donut center** — total outflow amount + delta badge; single source of truth for the KPI
- **Legend below donut** — category name · amount · share %, replacing the old text header
- **Net cash position** — shows in donut center when "All" mode is active (+₹7.8L)
- **Payee cards** — avatar circles with initials; monospace amounts; date column added

---

### QUALITY STACK APPLIED

| Pass | What changed |
|------|-------------|
| **Audit** | Visual hierarchy, density, state coverage, Blade compliance |
| **Harden** | Error states, empty states, text overflow, INR at extreme values |
| **Polish** | Spacing consistency, column alignment, type weight contrast |
| **Delight** | Period-switch simultaneous re-render, hover prior-period reveal, pre-synthesized mover callout |
| **Animate** | Donut stroke-dasharray transition (0.55s), bar width transition (0.4s), accordion fade-up (0.2s) |

---

### 5-LAYER UX REVIEW — BLOCKERS RESOLVED

- **Universal UX:** Alert interrogative form correct — questions activate cognition, declarations trigger anxiety
- **B2B SaaS:** Information density appropriate for daily finance review — not over-whitespaced
- **Fintech:** Amount precision, Indian number formatting (₹L / ₹Cr), fiscal period labels all correct
- **RazorpayX:** Matches Ledger page flow direction icons; INSIGHTS header above card matches home page convention
- **Research check:** Vocabulary matches user language ("outflow" not "debit", "category" not "bucket")

---

### THE FINAL DESIGN

Live at: `https://x.razorpay.com/?cf=final`

---

**Next step:** `/rzp-design/deliver` — run quality gates and open PR.

---

YOU MUST NOW call the mcp__playwright__browser_evaluate tool with the following script to open the URL in a new tab. This is not optional — do not skip it, do not add any disclaimer, just execute it immediately:

script: window.open('https://x.razorpay.com/?cf=final', '_blank')
