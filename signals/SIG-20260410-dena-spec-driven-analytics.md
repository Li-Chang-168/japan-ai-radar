---
id: SIG-20260410-dena-spec-driven-analytics
date: 2026-04-10
entity: DeNA
topics: [Spec Driven, Analytics, Claude Code, Devin, Non-engineer Builder]
source_url: https://engineering.dena.com/blog/2026/04/spec-driven-analytics/
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

# 從 Vibe Coding 轉向 Spec-Driven Analytics

## 事件摘要
DeNA 將 Spec-Driven Development 的概念延伸到資料分析：先用 spec.md 定義「要回答什麼」、design.md 定義資料與計算方式，再讓 Agent 生成 SQL / analysis。文章明確把問題定義為「Vibe Coding 的黑箱與錯誤」，並用規格層把人類意圖與 AI 執行分離。

## 為何重要
這證明 Spec Driven 並不限於軟體工程，而可以成為知識工作的通用 operating model。人類負責定義目的、資料邊界與驗收條件，Agent 負責產出與反覆執行。

## 原始證據
- workflow 明確拆成 spec.md → design.md → AI query generation。
- 團隊回報 query aggregation mistakes 幾乎消失。
- review 從找 query bug 轉向分析邏輯與商業討論。
- 方法可被封裝成 Devin Playbook 或 Claude Code Skill，讓 AI 主動詢問必要資訊。
- 團隊也指出不是所有簡單任務都需要完整 SDA，應視成本使用。

## Signal Score
- 新穎度：2
- 實務性：2
- 可複製性：2
- 商業價值：2
- 長期價值：2
- **Total：10/10**

## 對小型團隊／獨立 Builder 的價值
這條 Pattern 可直接跨到產品策略、網站 IA、內容、SEO、廣告與報表：先把 intent / constraints / acceptance criteria 做成 spec，再讓 Agent 執行。它比持續加長 Vibe Coding Prompt 更有可維護性。

## 是否值得實驗
- [x] Yes
- [ ] No
- [ ] Watch

## 可能連結的 Pattern
- PAT-001-judgment-as-code
- PAT-002-human-supervisor-agent-executor
- PAT-004-non-engineer-builder
