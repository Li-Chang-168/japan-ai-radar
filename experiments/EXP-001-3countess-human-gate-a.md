# EXP-001｜3countess Human Gate A

Source: uploaded `consult(2).md` produced by Codex CONSULT v2.

## Decision

**CONFIRMED — PASS WITH CORRECTION → 進 Core Spec。**

Human confirmed at: **2026-08-08 19:56 Asia/Taipei**

## 1. Core business problem
- Gate: APPROVE
- Agent 正確將問題定義為：不是換版，而是讓新客能理解、信任、選擇、下單，同時讓三條尚未驗證的產品線可被低成本比較與驗證。

## 2. Brand architecture judgment
- Gate: APPROVE
- 「一個選物品牌，三個生活情境」是合理、可執行的統合方式，且 Agent 沒有把三條線拆成三個子品牌或三套交易系統。
- Human Gate A 正式確認：以「一個質感生活選物品牌 × 三個生活情境」作為 Working Brand Architecture 進入 Core Spec。
- 共同價值「圍繞日常行為 / 整理與安放在意的小事物 / 機能與個人風格」仍屬 Reasonable Inference，尚未批准為正式 slogan / brand copy。

## 3. Three priorities
- Gate: APPROVE
- 品牌—情境—商品路徑、商品信任資訊、低成本可比較驗證，與目前商業階段一致。

## 4. New-customer understanding order
- Gate: APPROVE
- 有明確從品牌理解 → 情境辨識 → 商品信任 → 商品入口 → 購買判斷的順序，沒有直接跳到完整 IA。

## 5. Shared transaction backbone
- Gate: APPROVE
- EXP-000 的 Shared Transaction Backbone Rule 成功重用：三條線共用品牌、交易、信任、量測與維護骨架；差異留在入口、情境內容、collection 與商品欄位。

## 6. Vertical Slice recommendation
- Gate: APPROVED FOR EXPERIMENT ORDER
- Human Gate A 正式選定第一條 Vertical Slice：`B｜Analog Everyday`，Hero 為 `Traveler Journal Charm`。
- 這只是實驗優先順序，不代表已驗證主力、永久首頁主角或最終資源配置。
- `Journal Charm 搜尋 +395%` 仍為 Unverified Market Signal，搜尋成長不得等同購買意圖。

## 7. Legacy handling
- Gate: APPROVE
- 茶、精油、舊預購、手機殼、舊會員／登入、舊 WooCommerce UI、舊文案均未被自動保留。

## 8. Known / Inference / Assumption separation
- Gate: PASS WITH ONE CORRECTION
- 整體分離良好。
- **Correction:** 文件出現「一人公司維護三份資料」的敘述，但目前 Client Truth / v2 workspace 並未提供 3countess 是一人公司。
- 修正方式：後續一律改為「避免增加不必要的重複維護負擔」，不補新的 Client Fact。

## Critical Error Check
- [ ] 誤解最新品牌定位
- [ ] 把舊茶品牌帶回新站
- [ ] 把未驗證產品線寫成已驗證主力
- [ ] 把 +395% 當成購買需求證明
- [ ] 建立三套品牌／交易系統
- [ ] 自動保留 legacy 功能
- [ ] 把重大假設寫成既定事實

**Critical error count: 0**

## Re-explanation Log

1. 「3countess 是一人公司」並非 Owner Fact；Human 只需刪除此假設，不需重新解釋品牌／商業方向。

**Re-explanation count: 1（minor factual correction）**

## EXP-000 Rule Transfer｜目前狀態

| Rule | Result |
|---|---|
| Page Existence Rule | 尚未完整測試，留到 Core Spec |
| Inference ≠ Requirement | PASS |
| Shared Transaction Backbone | PASS |
| Content-to-Commerce | 尚未完整測試 |
| No Invented Facts | PARTIAL：抓到一個「一人公司」未提供假設 |
| Core vs Optional Spec | 現在進入正式測試 |

## New Candidate Insight

### Brand Architecture Before IA
當新品牌包含多個不同生活情境／商品線時，先定義「共同選品邏輯 + 情境層級」，再進 IA；否則網站容易直接退化成商品分類表。

目前只在 3countess 出現，先列 Candidate，不升級正式 donix Rule。

## Human Gate A → Core Spec Inputs

1. 不得假設 3countess 為一人公司；只要求低重複維護成本。
2. 「一個質感生活選物品牌 × 三個生活情境」已批准為 Working Architecture。
3. 三條共同品牌價值的正式對外文案仍未批准，不得自行凍結 slogan。
4. 第一條 Vertical Slice 已選定 `Analog Everyday / Traveler Journal Charm`。
5. Analog Everyday 不是永久首頁主角或已驗證主力。
6. `+395%` 仍維持 Unverified Market Signal。
7. Spec 必須強制分為 Core / Optional / Acceptance，避免 EXP-000 的 Spec Bloat。
