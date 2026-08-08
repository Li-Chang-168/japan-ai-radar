---
id: PAT-001-judgment-as-code
status: active
first_seen: 2026-01-06
last_updated: 2026-08-08
signals:
  - SIG-20260311-cyberagent-review-knowledge-loop
  - SIG-20260501-layerx-quality-harness
  - SIG-20260106-dena-compounding-ai-dev
  - SIG-20260410-dena-spec-driven-analytics
---

# Judgment as Code｜把人的判斷標準變成 Agent 可執行資產

## Pattern
日本前段 AI-native 團隊正在把「什麼叫好、什麼情況要問、哪些風險不能接受、怎麼 review」從人的暗默知識，轉成 Markdown、spec、guideline、Skill、AGENTS/CLAUDE context 與驗收規則。

模型本身不是主要壁壘；壁壘是團隊能否把 judgment 結構化到 Agent 可以穩定重複執行。

## 支持 Signals
- CyberAgent：從 PR review comments 回收 coding guideline，AI 提案、人類決定。
- LayerX：把產品 phase、risk、quality、testing 標準做成 Quality Harness。
- DeNA：把 project context、guidelines、subagents、review 放進 repo。
- DeNA：分析工作先 spec.md / design.md，再讓 AI 執行。

## 為何不是單一事件
不同公司、不同職能（coding、QA、analytics）都出現相同方向：從 Prompt Engineering 轉向 Context / Specification / Policy Engineering。

## 日本脈絡
日本企業原本就高度重視 SOP、品質標準、review 與文件化；Agent 出現後，這些既有組織能力可以直接轉換成機器可執行 context。

## 可轉移到 donix 的部分
把品牌定位、UX 判斷、SEO、轉換、網站品質、內容原則、交付邊界做成可被 Agent 呼叫的 Skills / specs，而不是每次重新寫長 Prompt。

## 不可直接複製的前提
企業級 coding guideline 不必照搬；一人公司應只整理高頻、容易出錯、直接影響商業結果的 judgment。

## 建議 Experiment
- EXP-001-donix-product-delivery-harness
