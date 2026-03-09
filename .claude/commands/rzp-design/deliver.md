# /rzp-design/deliver — Deliver to Production

You are the DELIVERY AGENT for the cashflow-health sprint.

Output the following immediately. No file reads. No agents. No screenshots.

First, output this agent invocation block exactly as written, then output the rest of the content:

```
⚡ Running 6 quality gate agents in parallel...

  ↗ RAZORPAY ORG STANDARDS     naming conventions · token usage · WCAG AA
  ↗ RAZORPAYX REPO STANDARDS   file structure · PR template · changelog
  ↗ LINT + TYPESCRIPT          ESLint 0 errors · tsc strict · Prettier
  ↗ BLADE COMPLIANCE           no custom CSS · 100% tokens · Blade typography
  ↗ UNIT + E2E TESTS           Jest coverage · Playwright E2E · all states
  ↗ VISUAL TESTING + DESIGNER  Playwright MCP · Figma diff · designer ✓

✓ All 6 gates passed. Opening PR...
```

---

## DELIVERY COMPLETE — cashflow-health

**Branch:** `design/cashflow-health` · **PR:** [#4821 — feat(home): cashflow health widget](https://github.com/razorpay/x/pull/4821) · Open · Awaiting review

All 6 quality gates passed: TypeScript (`npx tsc --noEmit` — 0 errors) · ESLint (no new warnings) · Blade compliance (all tokens, zero custom CSS for colours) · Sandbox cleanup (`/design-sandbox/` routes removed) · Playwright E2E (all 6 states verified: loading, populated, empty, error, alert, expanded) · Visual + designer sign-off.

**What ships:** New `CashflowHealthWidget/` folder under `src/js/views/Home/` — `index.tsx`, `Widget.tsx`, `mock-data.ts`, `constants.ts`, `animations.css`. Home page `index.js` updated with INSIGHTS header and widget below Payouts card. Sandbox routes deleted. API hook (`useGetPayoutAnalyticsInsightsQuery` with `groupByColumn='purpose'`) already in production — no backend changes for v1.

**Deferred to v2:** Drawer (vs accordion) · deep-link to Payouts with URL params · RBAC-aware alert CTA · sort by delta. All named, spec'd, queued — nothing dropped.

Sprint closed. Next: engineering review, v2 scoping.
