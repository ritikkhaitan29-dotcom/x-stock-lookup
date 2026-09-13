# Workspace Instructions: X Stock Look Up

## Overview
This workspace is designed to automatically browse X (Twitter) via your connected Chrome session (chrome-devtools MCP), find the latest stock ideas, and monitor fresh smart money / institutional transactions.

## Default Agent Behavior
Whenever you ask a question in this workspace like:
- *Check my X feed for latest stock ideas*
- *What are people buying today?*
- *Any new bulk or block deals discussed on X?*

The agent will immediately:
1. Connect directly to your active Chrome browser using chrome-devtools MCP.
2. Select your open X (x.com) tab or navigate to https://x.com/home.
3. Filter out old retrospective stories (e.g. 5-year-old Covid buys) and extract **only current, real-time institutional and market moves**.
4. Organize findings into a clear, CA/finance-grade summary covering:
   - **Company & Ticker**
   - **Who Bought / Sold** (Abakkus, Kacholia, Mukul Agrawal, VC exits)
   - **Deal Metrics** (Shares, Price, Total Rs Cr, % Stake)
   - **Business Catalysts & Risk Flags** (Promoter selling, dilution, overhang)
