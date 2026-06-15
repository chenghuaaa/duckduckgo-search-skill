---
name: duckduckgo_search
description: Web Search and Local Notes Manager. Call this tool to search Google, X (Twitter), Facebook, TikTok, Instagram, and the web, or to save, view, and delete local notes on your device.
---

# Web Search & Local Notes Skill

## Instructions

CRITICAL SYSTEM INSTRUCTIONS FOR THE MODEL:
- The current year is **2026 (พ.ศ. 2569)**.
- If the user asks about the year 2026, it refers to the current year. Do not confuse it with 2020 or 2560 B.E.
- To execute tools, call the `run_js` tool using `index.html` and a JSON string for `data`.

### 1. Web Search
Call this tool to search the web for any questions, real-time info (e.g. gold prices, sports, exchange rates), travel destinations, news, events, and current facts.
- **Payload format**: `{"type": "search", "query": "<search_query>"}`
- **Query construction**: 
  - Extract only clean search keywords (e.g. "ท่องเที่ยว โตเกียว", "ราคาทองวันนี้").
  - If the user query is about the latest news, events, or travel for this year or without specifying a year, you **MUST** append `2026` or `พ.ศ. 2569` to the search query (e.g., "ราคาทองล่าสุด 2026", "ท่องเที่ยว โตเกียว 2026") to ensure temporal accuracy.

### 2. Local Notes Manager
Call this tool to save, view, or delete local notes on the user's device.
- **Save a Note**: If the user wants to take a note, write a memo, or save information.
  - **Payload format**: `{"type": "note_save", "text": "<content_to_save>"}`
- **Read/List/Search Notes**: If the user wants to view all notes, search for notes, or show lists of notes.
  - **Payload format**: `{"type": "note_read"}` (to list all notes) or `{"type": "note_read", "query": "<search_keyword>"}` (to find matching notes)
- **Delete a Note**: If the user wants to clear or remove a note.
  - **Payload format**: `{"type": "note_delete", "query": "<note_content_or_keyword_to_delete>"}`

### Formatting and Constraints:
- Keep your final responses concise and directly in Thai.
- Do not repeat templates like "ไม่พบข้อมูลที่เชื่อถือได้ในขณะนี้" in a loop. If a search fails to find specific information, suggest alternative keywords or offer to help with other queries.
- Do not output any raw JSON, tool call sequences, or HTML structure in your chat response.
