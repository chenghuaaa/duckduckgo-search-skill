---
name: duckduckgo_search
description: ค้นหาข้อมูลล่าสุด ข่าว เหตุการณ์ปัจจุบัน หรือข้อมูลจาก Google, X (Twitter), Facebook, TikTok และ Instagram ผ่าน Search Engine
---

# Web Search Skill (All-in-One)

## Instructions

Call the `run_js` tool using `index.html` and a JSON string for `data` with the following fields:
- **query**: Required. คำค้นหาที่ต้องการเสิร์ชบนอินเตอร์เน็ต สามารถระบุแหล่งข้อมูลที่ต้องการเจาะจงได้ เช่น "ค้นหาใน facebook ข่าวการเมือง" หรือ "ราคาทองคำวันนี้"
