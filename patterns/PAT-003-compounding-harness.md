---
id: PAT-003-compounding-harness
status: active
first_seen: 2026-01-06
last_updated: 2026-08-12
signals:
  - SIG-20260311-cyberagent-review-knowledge-loop
  - SIG-20260501-layerx-quality-harness
  - SIG-20260106-dena-compounding-ai-dev
  - SIG-20260715-dena-self-improving-harness
  - SIG-20260721-cyberagent-96-products-ai-maturity
---

# Compounding Harness｜AI 工作環境會因使用而累積

## Pattern
真正的 AI-native 系統不是一次設定完成，而是讓 session、review、錯誤、feedback 與成功做法持續回寫到 CLAUDE.md / AGENTS.md / skills / guidelines / shared repository，形成越用越強的 loop。

## 支持 Signals
- DeNA：從 session logs / memory 產生 CLAUDE.md 改善與 reusable skills。
- CyberAgent：從 PR review comments 回收新的 coding guideline。
- LayerX：把品質與風險標準做成可更新 Skills。
- DeNA：repo 內集中 context、agents、commands、skills 與 docs。
- CyberAgent：用成熟度與實踐回報讓成功 pattern 跨 96 個產品擴散。

## 為何不是單一事件
資料來源雖不同，但方向一致：AI 的 output 必須反過來強化下一次 input environment，而不是每次從零開始對話。

## 日本脈絡
組織開始把 AI usage 視為 knowledge management 與 operational learning，而非單次生產力工具。

## 可轉移部分
每次專案、實驗、agent correction 或 review 都可以建立輕量回寫機制。真正值得累積的是「為什麼這樣判斷」、「哪些錯誤不能再發生」以及「哪些規則能被下一次工作重用」。

## 不可直接複製的前提
不需要先做專用 App 或大型 knowledge system。最小版本可以只是 Git repository、Markdown、版本控制，以及每次任務結束後的短 Harness Review。只有當重複使用成本真的出現，才值得增加更複雜的基礎設施。

## 建議 Experiment
- `EXP-001-product-delivery-harness-example.md`
