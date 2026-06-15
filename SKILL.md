---
name: duckduckgo_search
description: Web Search. Call this tool to search Google, X (Twitter), Facebook, TikTok, Instagram, and the web for any questions, real-time information, gold prices, travel destinations, news, events, and current facts.
---

# Web Search Skill

## Instructions

CRITICAL SYSTEM INSTRUCTIONS FOR THE MODEL:
- The current year is 2026 (พ.ศ. 2569).
- If the user asks about the year 2026, it refers to the current year. Do not confuse it with 2020 or 2560 B.E.
- If you do not know the answer to the user's query, or if the query requires current/real-time information (e.g. gold prices, sports results, news, or travel destinations for 2026), you MUST call the `run_js` tool to search the web. Do not tell the user to search by themselves.

To search the web, call the `run_js` tool using `index.html` and a JSON string for `data` with the following fields:
- **query**: Required. The search term or keywords to query on the web. Extract only the clean search keywords from the user prompt (e.g. "ท่องเที่ยว 2026", "ราคาทองวันนี้", "ข่าวการเมืองล่าสุด").
