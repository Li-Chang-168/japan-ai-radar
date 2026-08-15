---
id: PAT-002-human-supervisor-agent-executor
status: active
first_seen: 2025-06-26
last_updated: 2026-08-12
signals:
  - SIG-20260216-cyberagent-two-engineers-ai-led-dev
  - SIG-20260721-cyberagent-96-products-ai-maturity
  - SIG-20250626-rakuten-autonomous-parallel-dev
  - SIG-20260410-dena-spec-driven-analytics
---

# Human Supervisor, Agent Executor｜人類從實作者轉成監督與決策者

## Pattern
前段團隊逐漸把人類角色從逐步實作移到 intent、priority、plan approval、trade-off 與 final review；Agent 則負責 research、planning、task decomposition、implementation、testing、review draft 與 PR。

## 支持 Signals
- CyberAgent：兩人工程團隊讓 AI 主導需求深挖到 review，人類主要做確認與決策。
- CyberAgent：成熟度模型把 Orchestrator、Architect、Workflow 視為更高階 AI 使用型態。
- Rakuten：多個 Claude Code session 並行，把工程師變成多工作流管理者。
- DeNA SDA：人先定 spec / design，AI 再執行 query 與分析。

## 為何不是單一事件
多家公司都不再以「AI 幫忙寫 code」描述成熟狀態，而以「AI 主導執行、人類設計邊界與 checkpoint」描述。

## 日本脈絡
不是追求完全無人，而是把 Human-in-the-loop 放在高風險、高判斷價值的位置。

## 可轉移部分
團隊可以把人類集中在問題定義、優先順序、規格批准、風險判斷與最終驗收，讓 Agent 負責研究、規格整理、實作、QA 草稿與文件化，但每一層自治都要有明確邊界。

## 不可直接複製的前提
沒有明確 spec、acceptance criteria、測試、權限邊界與回滾機制時，不應直接提高自治程度。

## 建議 Experiment
- `EXP-001-product-delivery-harness-example.md`
