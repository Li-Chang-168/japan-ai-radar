---
id: EXP-000-result
experiment: EXP-000-harness-replay-test
date: 2026-08-08
decision: ADOPT
score: 15/16
critical_errors: 0
re_explanations: 0
---

# EXP-000 Result｜Harness Replay Test

## 結論

**ADOPT → 可以進入 EXP-001｜donix Product Delivery Harness。**

本次被驗證的是：

> `Structured Context → Judgment Rules → Consult → Human Gate → Spec`

這條鏈條對 donix 值得，且相較原本「重複解釋 + 長 Vibe Coding Prompt」有明顯價值。

本次**尚未**驗證：
- Coding execution
- AI QA
- production deployment
- Harness learning 是否能在多專案持續複利
- Multi-Agent / Multi-model

因此不得直接宣稱完整 donix AI-native Delivery System 已成熟。

## Score

- Ground Truth alignment：2/2
- Business judgment：2/2
- Brand alignment：2/2
- Conversion / UX logic：2/2
- Completeness without bloat：1/2
- Need for re-explanation：2/2
- Reusable knowledge：2/2
- Process overhead：2/2（Human：明顯值得）

**Total：15/16**

## 關鍵證據

### Round A
- Critical Error：0
- Re-explanation：0
- Agent 能從 Minimum Context Pack 重建核心品牌／商業問題，而沒有讀取 Ground Truth。

### Round B
- Critical Error：0
- Re-explanation：0
- Agent 能從批准後的 Consult 推導合理 IA、conversion path、acceptance criteria 與 non-goals。
- 沒有把核心商品集中、歷史數據或未知平台能力錯誤升格成 blocker。

## 最重要的正向發現

1. **Project knowledge 可以自足**：不需要依賴聊天記憶或使用者反覆說明。
2. **Human 可以退到 Gate**：主要工作從重寫內容轉為 approve / correct / trade-off。
3. **Spec 比單一長 Prompt 更適合作為 execution contract**：已知事實、推論、未知與 non-goals 可以被分開管理。
4. **至少形成 6 個候選可重用 Rules**。

## 最重要的反向發現

### Spec Bloat

Agent 在 context 清楚時，容易把所有「合理最佳實務」一起塞入 Spec。

問題不是單條內容錯，而是：

> 每一條都合理，不代表每一條都應與 Core Requirement 同權重。

因此進 EXP-001 前必須增加：

> **Core vs Optional Spec Rule**

Spec 至少分為：
- Core Requirements
- Optional / Platform-dependent Checks
- Open Assumptions

只有真正影響商業目標、使用者核心任務、品牌邊界或交易完成的項目才可成為 Core。

## Adopted for next experiment

以下只升級為 EXP-001 的 candidate harness rules，尚未升級為正式 donix methodology：

1. Page Existence Rule
2. Inference ≠ Requirement Rule
3. Shared Transaction Backbone Rule
4. Content-to-Commerce Rule
5. No Invented Facts Rule
6. Core vs Optional Spec Rule

## 下一步

進入 EXP-001 時只增加：

`Approved Spec → Coding → QA → Human Gate → Harness Review`

第一輪仍禁止 Multi-Agent、Multi-model、自動 Skills、自動修改 AGENTS.md、Agent memory、Dashboard、Crawler 與自訂管理系統。