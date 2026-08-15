---
id: SIG-20260106-dena-compounding-ai-dev
date: 2026-01-06
entity: DeNA
topics: [Claude Code, Cursor, Subagents, CI, Knowledge Management]
source_url: https://engineering.dena.com/blog/2026/01/ai-driven-develop/
source_type: company_engineering_blog
score:
  novelty: 1
  practicality: 2
  replicability: 2
  business_value: 2
  long_term_value: 2
  total: 9
status: active
---

# AI 開發體制從個人助手升級成可累積的團隊系統

## 事件摘要
DeNA 在複雜新服務中，把 Claude Code / Cursor 從個人輔助工具升級為 repository-level system：CLAUDE.md、AGENTS.md、專用 subagents、commands、skills、docs 與 Claude Code Actions 自動 review 串成完整工作流。

## 為何重要
關鍵在「context 與 workflow 都進 repo」。Agent 不是臨時聊天對象，而是讀得到專案脈絡、遵守規則、接受自動 review、並隨文件更新持續改善的團隊成員。

## 原始證據
- repo 內集中 CLAUDE.md、AGENTS.md、agents、commands、skills、development guidelines。
- PR 建立後，依變更檔案類型啟動專門 review agent。
- workflow 包含 implementation、review、knowledge accumulation 三階段。
- 目標是降低 review 量並標準化 output quality。

## Signal Score
- 新穎度：1
- 實務性：2
- 可複製性：2
- 商業價值：2
- 長期價值：2
- **Total：9/10**

## 對小型團隊／獨立 Builder 的價值
直接支持「每個產品 repo 本身就是 Agent 工作環境」的方向。專案知識、交付規則、QA、內容與 deployment 不應散在聊天紀錄，而應存在 repo 並能被 Agent 自動讀取。

## 是否值得實驗
- [x] Yes
- [ ] No
- [ ] Watch

## 可能連結的 Pattern
- PAT-001-judgment-as-code
- PAT-003-compounding-harness
