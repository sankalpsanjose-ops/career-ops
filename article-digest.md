# Article & Project Digest
# Proof points, project detail, and context for the model to draw from during evaluations and CV generation.
# This is NOT the CV — it's the richer background layer.

---

## Patent: Enhancing Item Retrieval Using Fitment Match (eBay, filed Dec 2024)

**Status:** US Patent Application filed — Sankalp Arun Patil is a named co-inventor  
**Docket:** IP-P3864US1 / Application No. 428838  
**Assignee:** eBay Inc.  
**Co-inventors:** Sarabdeep Singh Multani, Suhas Giridhar Danavandi, Prathihasth Rekabu, Saurabh Dubey, Sankalp Arun Patil

**What the invention does:**  
Automotive parts on eBay have "fitments" — compatibility metadata (year/make/model of car a part fits). The patent covers a system that:
1. Generates a hash per fitment for each part listing
2. Clusters part listings based on **fitment match** (overlap of fitment hash sets) — identifying interchangeable parts across sellers
3. Uses these clusters to **expand search recall** and **improve recommendations** — returning interchangeable parts the user might not find through keyword search alone
4. Supports exact (100%) or threshold-based (e.g., 80%) fitment overlap, with optional price/category signals to prevent false clustering

**Scale context:** Patent cites eBay's 1.7 billion listings and ~3 billion monthly visits — this system operates at that scale.

**Talking points:**
- "I co-invented a fitment-based clustering system for eBay Motors search — it improves recall by grouping interchangeable parts across listings, so a search for a part number surfaces all equivalent listings, not just exact-match ones."
- "The core insight was treating compatibility metadata as a clustering signal rather than a filter — similar to how you'd use embeddings for semantic similarity, but deterministic and explainable."
- "This is now a filed US patent assigned to eBay — the team went through formal IP review and prosecution."

**Relevant for:** Analytics Lead, Senior Product Analyst, Search/Recommendation Engineer, Applied Scientist, Data Scientist roles — demonstrates production-scale data engineering and IR work with institutional validation (US patent).

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

---

## Project: Emowear

**What it is:** Web app that decodes subtext in high-stakes workplace conversations and generates calibrated response options.
**Links:** github.com/sankalpsanjose-ops/emowear

**What it does:**
- User pastes a meeting statement or transcript
- Claude analyzes subtext: passive-aggression, implied blame, credibility challenges, power dynamics
- Returns three distinct response options tuned to different communication styles (direct, diplomatic, assertive)
- Profiles remember your communication personality over time via auto-inferred notes
- 7-day stress tracking dashboard across conversation history

**Technical detail:**
- Claude API with `tool_use` for structured JSON responses (not freeform text)
- System prompt (~60 lines) with explicit guardrails: 15-word max per response, no corporate jargon, conversational tone enforced
- 957 lines TypeScript; clean separation across lib/, app/, components/
- localStorage persistence (no backend DB — deliberate for privacy)
- Jest + React Testing Library coverage
- Iterated to v0.5 based on real user feedback: added profiles, stress meter, personality tracking

**What makes it interesting for roles:**
- Shows product thinking beyond the model: UX iteration, edge case handling, privacy-first architecture choice
- `tool_use` integration is more sophisticated than prompt-in/text-out — structured outputs, validation, error handling
- Self-improving profile layer (learns communication style over time) mirrors agentic memory patterns

**Talking points:**
- "I used tool_use instead of freeform generation because I needed guaranteed structured outputs — the UI renders three distinct response cards, so I needed deterministic JSON, not prose."
- "The personality notes are auto-inferred from patterns across conversations — the user never fills a form, it just learns from usage."

---

## Project: Coaster (Claude Code Plugin)

**What it is:** A Claude Code plugin that monitors cognitive wellness during long coding sessions and nudges you to take breaks or hand off context.
**Links:** github.com/sankalpsanjose-ops/coaster

**What it does:**
- Hooks into Claude Code's UserPromptSubmit, Stop, and SessionStart events
- Detects four signals: overwork (>90 min session), cognitive debt (Claude doing 85%+ of thinking), repetitive loops (same approaches detected via response hashing), stress (frustrated keyword frequency)
- Delivers personality-flavored nudges: "peer_coder", "drill_sergeant", "zen_master"
- On handoff: generates structured summary (current state, open threads, first move) so you don't lose context

**Technical detail:**
- Pure Node.js hooks, no external services or dependencies
- State stored in JSON files at ~/.claude/coaster/
- 807 lines of production code + 40 unit tests (Jest)
- Two-tier cooldown: 5 turns after firing, 20 turns after dismissal — prevents intrusiveness
- Response hashing for loop detection (not keyword matching — actual structural similarity)
- Top-level try/catch on all hooks + silent fail mode so it never breaks Claude Code

**CV usage guidance:**
- Include when applying to: developer tools companies, AI-native startups, roles that mention "Claude Code", "MCP", "agent tooling"
- Skip or downplay for: pure data science, analytics, or business roles where the reader won't know what a Claude Code plugin is
- Best framing: "built a local dev tool that hooks into the Claude Code runtime to monitor session health" — accessible without assuming knowledge
