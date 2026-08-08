---
id: SIG-20260715-dena-self-improving-harness
date: 2026-07-15
entity: DeNA
topics: [Claude Code, Agent Harness, Knowledge Management, Skills, MCP]
source_url: https://engineering.dena.com/blog/2026/07/claude-code-harness-app/
source_type: company_engineering_blog
score:
  novelty: 2
  practicality: 2
  replicability: 2
  business_value: 2
  long_term_value: 2
  total: 10
status: active
---

# 從 Session Log 反向培養 Agent Harness

## 事件摘要
DeNA 開發「geni ハーネスくん」，把 Claude Code 的 session logs、memory、CLAUDE.md、rules 與 skills 串成持續改善循環：從實際使用紀錄找出反覆說明與修正，產生 CLAUDE.md 改善案或新的 reusable skill，再由人類確認後套用。

## 為何重要
這把 Harness 從靜態設定檔變成會從工作歷史學習的資產。真正的複利來源不是模型升級，而是把「使用過程中的暗默知識」持續回收、結構化、分享。

## 原始證據
- 從 session / memory 生成 CLAUDE.md 差異改善案。
- 可將個人知識生成 skill 並安裝回 ~/.claude/skills。
- 建立組織共享 harness catalog，讓 rules / skills 可跨人員重用。
- 分享前經過機械掃描 + AI 掃描，且所有變更保留 human approval。
- 支援非工程師透過 UI 管理 MCP、skills 與日常 review loop。

## Signal Score
- 新穎度：2
- 實務性：2
- 可複製性：2
- 商業價值：2
- 長期價值：2
- **Total：10/10**

## 對 donix / 一人公司的價值
這可能是 Radar 最重要的長期 Pattern：每次使用 Codex / Claude Code 的修改紀錄，都能成為下一版 AGENTS.md、Skill 或 checklist 的原料。你的個人經驗可逐步變成可重複交付的組織能力，即使組織只有一人。

## 是否值得實驗
- [x] Yes
- [ ] No
- [ ] Watch

## 可能連結的 Pattern
- PAT-003-compounding-harness
- PAT-001-judgment-as-code
- PAT-004-non-engineer-builder
