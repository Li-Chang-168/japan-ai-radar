---
id: SIG-20260311-cyberagent-review-knowledge-loop
date: 2026-03-11
entity: CyberAgent / AmebaLIFE
topics: [Claude Code, Human-in-the-loop, Knowledge Loop, Coding Guidelines, GitHub Actions]
source_url: https://developers.cyberagent.co.jp/blog/archives/62639/
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

# 把 Review 暗默知識自動回收成 Agent 可讀規則

## 事件摘要
CyberAgent AmebaLIFE 將 PR review comments 定期收集、交由 AI 整理成 coding guideline 候選，再由人類決定是否採用；更新後的 guideline 同時供人與 AI review 參照。

## 為何重要
這建立了真正的 compounding loop：工作產生 feedback → feedback 轉成規則 → 下一次 Agent 直接使用。AI 系統不是靠一次寫好的 prompt，而是從實際錯誤與判斷持續變強。

## 原始證據
- GitHub Actions 定期收集 review comments 並建立 guideline candidate PR。
- Human-in-the-loop 保留「是否成為規範」的最後判斷。
- 團隊已觀察到 Claude Code review 開始依照累積 guideline 指出問題。
- 人類 review 因此可更集中於 specification 與 business logic。

## Signal Score
- 新穎度：2
- 實務性：2
- 可複製性：2
- 商業價值：2
- 長期價值：2
- **Total：10/10**

## 對小型團隊／獨立 Builder 的價值
這很適合把「每次修正 Agent 的理由」轉成長期資產：產品判斷、UX 規則、品質檢核與交付規格，不應每次重講，而應從修正紀錄回寫到 AGENTS.md / Skills / checklists。

## 是否值得實驗
- [x] Yes
- [ ] No
- [ ] Watch

## 可能連結的 Pattern
- PAT-001-judgment-as-code
- PAT-003-compounding-harness
