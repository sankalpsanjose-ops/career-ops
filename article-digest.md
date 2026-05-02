# Article & Project Digest
# Proof points, project detail, and context for the model to draw from during evaluations and CV generation.
# This is NOT the CV — it's the richer background layer.

---

## Project: Claude Trader

**What it is:** Autonomous multi-agent trading system built with Claude API. Live on Vercel.
**Links:** claude-trader-delta.vercel.app · github.com/sankalpsanjose-ops/claude-trader

**Architecture:**
- 6-agent hierarchy: Alpha (market data), Bravo (technical analysis), Charlie (sentiment/macro), Delta (fundamentals) run in parallel → Echo (synthesizer, conflict detection, conviction scoring) → Foxtrot (portfolio manager, final execution)
- 3-stage Vercel Cron pipeline: daily analysis (10:05 AM UTC), trade execution at market open (3:50 AM UTC weekdays), monthly reflection (1st of month)
- Monthly self-reflection loop: Claude reviews 30-day trading performance, identifies behavioral drift, and rewrites its own decision rules in Supabase — no human intervention

**Stack:** Next.js 16 / React 19 / TypeScript, Anthropic Claude SDK (claude-sonnet-4-6), Supabase (PostgreSQL), Yahoo Finance API, shadcn + Recharts, Vercel

**Risk controls built in:**
- Minimum 10% cash reserve enforced programmatically
- Max 20% portfolio allocation per position
- Sector diversification tracking
- Full audit trail in Supabase (every decision logged with rationale)

**What makes it interesting for AI/Data roles:**
- Demonstrates real agentic system design, not just prompt calling
- Self-improving feedback loop is a sophisticated pattern (few engineers have shipped this)
- Financial domain adds credibility: P&L tracking, fee calculations, market calendar logic
- Fully deployed and automated — not a demo or notebook

**Talking points for interviews:**
- "I designed the agent topology so specialists run in parallel, the synthesizer explicitly flags where agents disagree — the portfolio manager then has to resolve conflicts, not just average them."
- "The monthly reflection isn't just logging — the AI actually rewrites its own trading profile based on what worked. The decision rules in month 3 look nothing like month 1."
- "I chose Vercel Crons over a traditional scheduler because the system needed to be stateless between runs — each cron fetches fresh context from Supabase, so there's no drift from in-memory state."

---

## Official Employment Details (for application forms)

- **Current official title:** Manager, Business Analytics 1
- **Employer:** eBay
- **CV functional title:** Product & Data Science Analytics Lead
- Note: eBay uses internal leveling titles that don't reflect scope. The functional title is used externally and is accurate to the work performed.

---

## More projects to be added
<!-- Add second project (tough conversations dashboard) here once shared -->
