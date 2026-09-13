---
name: x-stock-lookup
description: >
  Autonomous workflow for browsing X (Twitter) via Chrome DevTools MCP to track
  fresh stock tips, institutional smart money movements (bulk/block deals), fund
  manager portfolio actions (Abakkus, Kacholia, Mukul Agrawal), and market chatter.
---

# X Stock Lookup Workflow

## Objective
When this workspace is active, the agent autonomously connects to the user's logged-in Chrome session via Chrome DevTools MCP, browses X (Twitter), filters out retrospective noise/historical stories, and extracts actionable, fresh institutional and market investment data.

---

## Chrome DevTools Connection Standard

1. **Default Tool:** Always use chrome-devtools MCP.
2. **Page Detection:**
   - Call list_pages to locate the active x.com or 	witter.com tab.
   - If an X tab exists, select it using select_page.
   - If no X tab is open, call 
ew_page or 
avigate_page to https://x.com/home.
3. **Session State:**
   - Rely on the user's active login/cookies in Chrome.
   - Never attempt to re-login or ask for Twitter API credentials.

---

## Execution Modes

### Mode 1: Feed Scan (Live Timeline)
Use this when the user asks: What is my feed talking about? or Check my timeline for stocks.

1. Target https://x.com/home.
2. Extract visible articles using evaluate_script:
   Fetch visible tweets (author, datetime, text content).
3. Scroll down using window.scrollBy(0, 2200) and extract 2-3 batches to capture sufficient breadth.

### Mode 2: Targeted Smart Money & Institutional Deals
Use this when looking for high-conviction institutional buys, bulk/block deals, or marquee investors:

1. Navigate to live targeted search URL:
   https://x.com/search?q=(bought%20OR%20stake%20OR%20%22bulk%20deal%22%20OR%20%22block%20deal%22)%20(Abakkus%20OR%20Ashish%20Kacholia%20OR%20%22Sunil%20Singhania%22%20OR%20%22Mukul%20Agrawal%22)&f=live
2. Extract tweets matching current date/week.
3. For broader exchange deals:
   https://x.com/search?q=(%22bulk%20deal%22%20OR%20%22block%20deal%22)%20(NSE%20OR%20BSE)%20-filter%3Areplies&f=live

---

## Filtering & Financial Discipline Rules

1. **Discard Retrospective Noise:**
   - Automatically ignore historical multi-bagger retrospectives (e.g. Covid crash buys 5-6 years ago) or generic motivational quotes.
   - Focus exclusively on **current transactions** (past few days / current week).
2. **Key Metrics to Extract:**
   - **Company Name & Ticker** (NSE/BSE).
   - **Institutional Investor / Fund Name** (e.g., Abakkus, Sunil Singhania, Accel exit, etc.).
   - **Transaction Details:** Buy vs Sell, Number of Shares, Price per Share, Total Rs Outlay, Stake %.
   - **Thesis & Catalysts:** Business drivers, margin triggers, order books, or corporate restructurings cited by analysts.
   - **Risk / Counter-view:** Promoter selling, valuation concerns, overhang.
3. **Fact & Price Verification:**
   - Quickly cross-check ticker CMP, 52-week High/Low against Yahoo Finance / NSE.

---

## Output Structure for User
Present results clearly in finance professional format:

1. **TL;DR:** 2-3 line executive summary of the biggest move.
2. **Institutional Smart Money Breakdown:** Structured tables showing Buyer, Seller, Price, Value (Rs Cr), Stake %.
3. **Investment Rationale & Business Drivers:** Core catalysts driving the interest.
4. **Counter-Signals / Risks:** Promoter selling, supply overhang, valuation flags.
