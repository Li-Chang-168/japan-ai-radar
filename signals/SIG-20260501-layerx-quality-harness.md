---
id: SIG-20260501-layerx-quality-harness
date: 2026-05-01
entity: LayerX
topics: [Claude Code, Agent Skills, Quality Harness, Testing, Human-in-the-loop]
source_url: https://tech.layerx.co.jp/entry/articulatin_quality
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

# 把品質與風險判斷做成 Quality Harness

## 事件摘要
LayerX 將產品階段、風險等級、自動測試責任與品質目標明文化後，實作成 Claude Code Agent Skills，讓 Agent 在實作前先判斷產品 phase 與 risk，再自動套用不同標準。

## 為何重要
這代表 AI-native 的關鍵不是 prompt 技巧，而是把「什麼叫好」與「什麼情況要更嚴格」結構化。模型負責執行，人類負責定義品質函數。

## 原始證據
- Skill 會判斷產品 phase，不確定時透過 HITL 詢問。
- 依功能風險讀取對應 context，避免一次塞入所有資訊造成 compaction。
- 自動套用實作方針、測試策略與 coverage 標準。
- 文章測試案例中，沒有 Skill 的 test coverage 為 65%，使用 Skill 後為 95%。

## Signal Score
- 新穎度：2
- 實務性：2
- 可複製性：2
- 商業價值：2
- 長期價值：2
- **Total：10/10**

## 對小型團隊／獨立 Builder 的價值
可以把產品、UX、內容、轉換與技術風險等判斷變成「分情境套用」的 Quality Harness，而不是一份無限變長的大 Prompt。這有助於降低精實交付的品質波動。

## 是否值得實驗
- [x] Yes
- [ ] No
- [ ] Watch

## 可能連結的 Pattern
- PAT-001-judgment-as-code
- PAT-003-compounding-harness
