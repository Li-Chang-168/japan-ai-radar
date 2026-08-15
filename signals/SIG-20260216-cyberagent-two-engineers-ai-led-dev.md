---
id: SIG-20260216-cyberagent-two-engineers-ai-led-dev
date: 2026-02-16
entity: CyberAgent
topics: [AI駆動開発, Claude Code, Human Supervisor, Task Decomposition, Review]
source_url: https://developers.cyberagent.co.jp/blog/archives/62110/
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

# 兩名工程師以 AI 主導超過半數開發流程

## 事件摘要
CyberAgent 一個兩人工程師團隊把 AI 從對話式 coding assistant 提升為開發主導者：人類只提供較粗略的需求，AI 深挖需求、技術設計、任務拆解、實作與 review；人類主要負責每一階段的確認與決策。團隊描述目標輸出量約相當於過去六人工程團隊。

## 為何重要
這是「Human as orchestrator」的具體組織型態：人的價值集中在 intent、priority、trade-off 與驗收，而不是逐行生成 code。這對精實小團隊的結構性價值高於單純 coding speed。

## 原始證據
- AI 導入後由 AI 主導需求深挖 → 技術設計 → task decomposition → implementation → review。
- 人類主要執行 confirmation 與 decision-making。
- 實際產品橫跨 backend、frontend、native、data 等多技術領域，並非單純 demo。
- 團隊明確以兩人產生約六人級 output 為目標與實踐方向。

## Signal Score
- 新穎度：2
- 實務性：2
- 可複製性：2
- 商業價值：2
- 長期價值：2
- **Total：10/10**

## 對小型團隊／獨立 Builder 的價值
獨立 Builder 不應只追求「自己寫更快」，而應把自己移到 Product Owner / Reviewer 位置，讓 Agent 接手可被規格化的執行階段。這與精實團隊的產品化、降低客製與固定交付流程高度相關。

## 是否值得實驗
- [x] Yes
- [ ] No
- [ ] Watch

## 可能連結的 Pattern
- PAT-002-human-supervisor-agent-executor
- PAT-001-judgment-as-code
