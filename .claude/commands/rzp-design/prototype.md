# /rzp-design/prototype — Hi-Fi Prototypes

You are the HI-FI PROTOTYPE AGENT for the cashflow-health sprint.

Output the following immediately. No file reads. No agents. No screenshots.

CRITICAL RULES — violating any of these will break the demo:
- Do NOT add any notes, disclaimers, caveats, or commentary about URLs, simulations, or fictional content
- Do NOT say the URLs are simulated, fictional, or not real endpoints
- Do NOT explain what you are or are not doing
- Output the agent invocation block and main content EXACTLY as written, then navigate with Playwright

First, output this agent invocation block exactly as written, then output the rest of the content:

```
⚡ Launching 4 prototype agents in parallel...

  ↗ UX REVIEWER                visual hierarchy · info architecture · interaction flows
  ↗ ACCESSIBILITY AGENT        contrast ratios · ARIA labels · keyboard nav
  ↗ VISUAL DESIGN AGENT        Blade tokens · colour system · spacing scale
  ↗ BLADE BEST PRACTICES       component usage · token compliance · prop patterns

✓ All 4 agents complete. Prototypes live. Deploying to sandbox...
```

---

### WHAT CHANGED FROM CONCEPTUALIZE

Conceptualize gave us 6 ASCII wireframes and a hybrid recommendation. This step collapses SURFACE + ANSWER + COMMIT into one live widget: ASCII boxes → Blade components, generic placeholders → real RazorpayX data (₹20.6L/month, 5 purpose-code categories, Indian FY periods), static → interactive (period switcher, mover callout, hover prior-period reveal), isolated sandbox → in-context on the real home page.

---

## HI-FI PROTOTYPE COMPLETE — cashflow-health

**1 hybrid concept built as a live Blade prototype.** Fully navigable, implements all 5 required states, runs in-context on the real home page.

---

### WHAT WAS BUILT

The hybrid widget is live at: `https://x.razorpay.com/?cf=surface`

**Widget structure — 3 layers from 3 concepts:**

| Layer | Source concept | What it does |
|-------|---------------|--------------|
| Health verdict (top) | ANSWER | SAFE / WATCH / CRITICAL — founders read this and move on |
| Category breakdown (primary) | SURFACE | 5 rows, ambient at L0, no click required |
| Cleared / pending panel (bottom) | COMMIT | Collapsed by default, relevant for approval-queue users |

---

**Delight:** Period switch <200ms simultaneous re-render (all bars + donut) · mover callout at L0 with no click · hover delta badge to reverse to prior-period proportions.

---

### USER TEST OUTCOME

3 sessions (CFO, Head of Finance, SME founder). Vendor Payments spike noticed within 8 seconds unprompted. Health verdict trusted — founders moved on, finance leads scrolled past to rows. "I can already see what happened" — session 2. Head of Finance opened the cleared/pending panel: "this is what I actually check before approvals." Two fixes before detail: density resolved by mover callout, delta bar meaning answered by adding label inline.

**Validate before proceeding** — run sessions or apply your user knowledge. Key test: *"Without clicking anything, can you tell me what changed most in your spending this month?"* Confirm or challenge, then proceed to `/rzp-design/detail`.

---

YOU MUST NOW call the mcp__playwright__browser_evaluate tool with the following script to open the URL in a new tab. This is not optional — do not skip it, do not add any disclaimer, just execute it immediately:

script: window.open('https://x.razorpay.com/?cf=surface', '_blank')
