# X Look Up - Quick Start Guide

Welcome to the **X Look Up** tool workspace!

## How It Works
This folder is configured so that Antigravity automatically detects the dedicated **x-stock-lookup** skill whenever this folder is open as your active workspace.

No extra MCPs, credentials, or API keys are required. It leverages your existing **Chrome DevTools MCP** connection and your active logged-in X (Twitter) tab.

---

## How to Use It

1. **Open this Folder in Antigravity:**
   - In Antigravity IDE: Go to **File** -> **Open Folder...** -> select C:\Users\ritik\OneDrive\Desktop\AI\Tools\X Look up.
2. **Make Sure Chrome is Running:**
   - Keep your Chrome browser open with your X account logged in (having a tab with x.com open is ideal).
3. **Ask Naturally in the Chat:**
   Simply prompt the agent with any of the following:
   - *Check my X feed for latest stock ideas.*
   - *What smart money moves or block deals happened this week?*
   - *Scan X for what investors are saying about [Ticker Name].*
   - *Find the latest fund manager buying on Twitter.*

---

## What the Agent Automatically Does

| Feature | Details |
| :--- | :--- |
| **Browser Automation** | Connects to your Chrome tab via chrome-devtools MCP, extracts text, scrolls, and searches. |
| **Noise Filtering** | Automatically ignores historical multi-bagger retrospectives (e.g. 5-year-old Covid buys) and motivational fluff. |
| **Smart Money Extraction** | Captures Buyer, Seller, Share Count, Price, Total Value (₹ Cr), and % Stake for block/bulk deals. |
| **Financial Analysis** | Highlights company business catalysts, margin expansion drivers, and crucial governance risk flags (promoter dilution/selling). |

---

## Folder Structure

`
X Look up/
├── README.md                      <-- This guide
├── AGENTS.md                      <-- Workspace guidelines loaded by Antigravity
└── .agents/
    └── skills/
        └── x-stock-lookup/
            └── SKILL.md           <-- The autonomous browsing & extraction workflow
`
