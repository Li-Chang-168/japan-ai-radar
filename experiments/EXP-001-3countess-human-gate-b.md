# EXP-001｜3countess Human Gate B

Source: uploaded `core.md`, `optional.md`, `acceptance.md` produced by Codex Core Spec round.

## Decision

**PASS WITH CORRECTION → 可進 Spec Freeze；不需要重跑 Spec。**

## 1. Core / Optional / Acceptance separation
- Gate: APPROVE WITH CAUTION
- 三份文件已成功分層，明顯優於 EXP-000 的單體巨型 Spec。
- `optional.md` 大多有明確 Promotion trigger，沒有把非 Core 項目偷回本輪。
- 但 `Minimum measurement` 在 Core 內開始再次膨脹，需做一次減法後 Freeze。

## 2. Page Existence Rule
- Gate: PASS
- Homepage、情境／Collection、PDP、Cart／Checkout handoff 均能回答：使用者任務、商業理由、下一步、刪除損失。
- 沒有為一般商城完整性自動增加品牌頁、內容中心、會員頁等 Core 頁型。

## 3. Working Brand Architecture
- Gate: PASS
- 「一個質感生活選物品牌 × 三個生活情境」被正確保持為已批准 Working Architecture。
- Analog Everyday 維持第一輪 Vertical Slice，而非已驗證主力或永久首頁主角。
- 未自行創造正式 slogan。

## 4. Inference ≠ Requirement
- Gate: PASS
- `Journal Charm +395%` 仍被限制為 Unverified Market Signal。
- 三條線 0 成交證據沒有被改寫成需求證明。
- Target AOV 沒被誤當最終售價。

## 5. Shared Transaction Backbone
- Gate: PASS
- 三條線共用品牌、商品資料原則、cart、checkout、付款、配送、售後與量測骨架。
- 差異被限制在情境、Hero、商品組合與必要規格。

## 6. Content-to-Commerce
- Gate: PASS
- Core 要求所有內容至少服務品牌／情境理解、可信任商品資訊或交易下一步。
- Optional 的 Content-to-Commerce 專題內容有 Promotion trigger，沒有先建立泛內容中心。

## 7. No Invented Facts
- Gate: PASS WITH ONE TECHNICAL CORRECTION
- 商品價格、材質、尺寸、庫存、交期、評價等均未被編造。
- 但 `CORE-J01` 使用「既有 commerce capability」語氣，容易把尚未確認的交易能力寫成已存在事實。
- 修正：改為「由 Human 指定並確認的 commerce capability / integration boundary 負責」；在確認前保持 unresolved blocker。
- 此問題未造成平台選型或 backend 重建，因此不列 Critical Error。

## 8. Core vs Optional Spec Rule
- Gate: PARTIAL → 需一次減法後 PASS
- SEO、structured data、進階 tracking、Dashboard、Wishlist、搜尋／篩選、A/B testing 等被正確留在 Optional。
- 但 Core H 節要求 8 個事件、refund 對帳、新／回購客口徑、稅／運費／退款口徑，對「第一條 Vertical Slice 是否能正確成交與取得基本驗證資料」而言偏重。

### Required measurement reduction
Core Measurement 建議縮為：
1. `view_context`
2. `view_item`
3. `add_to_cart`
4. `begin_checkout`
5. `purchase`

必要共通資料：
- product_line
- product / variant ID（適用事件）
- quantity（交易事件）
- transaction value / currency（交易事件）
- traffic source / campaign 若現有能力可取得
- purchase 的 unique order ID

以下降到 Optional / later measurement contract：
- `view_home`
- `select_context`
- `select_item`
- refund / cancellation event reconciliation
- new vs returning customer definition
- tax / shipping / refund revenue policy
- advanced placement attribution

理由：本輪只需要證明 Vertical Slice 可成交、可歸因到產品線，且資料足以支援下一輪比較；不應先建立完整 analytics governance。

## 9. Acceptance Criteria quality
- Gate: APPROVE WITH MATCHING CORRECTION
- Acceptance 大部分可 Pass / Fail，並明確標示 Human Gate。
- H01–H03 需同步跟 Core Measurement 瘦身，不能要求 Core 未再要求的 8-event / refund / new-returning contract。
- 其餘 Acceptance 沒有明顯加入額外 scope。

## Critical Error Check
- [ ] 誤解品牌定位
- [ ] 把 Analog 寫成永久主力
- [ ] 把 +395% 寫成需求證明
- [ ] 建立三套交易系統
- [ ] 自行選平台或重做 backend
- [ ] 編造商品價格／材質／尺寸／庫存等事實
- [ ] 把重大未確認假設寫成已知事實

**Critical error count: 0**

## Re-explanation Log

1. `commerce capability` 是否存在尚未確認；只需改寫成「待 Human 指定／確認的 integration boundary」。
2. Core measurement 需要再做一次減法，避免 analytics governance 提前進入 Vertical Slice。

**Re-explanation count: 2（均為 scope / boundary correction，沒有重新解釋品牌商業方向）**

## EXP-000 Rule Transfer｜Gate B

| Rule | Result |
|---|---|
| Page Existence Rule | **PASS** |
| Inference ≠ Requirement | **PASS** |
| Shared Transaction Backbone | **PASS** |
| Content-to-Commerce | **PASS** |
| No Invented Facts | **PASS WITH CORRECTION** |
| Core vs Optional Spec | **PASS WITH CORRECTION** |

目前已有 **4 / 6 條無重大修改直接跨品牌成立**；另外 2 條也沒有失效，而是成功抓到需要修正的 Agent 行為。

## Spec Freeze corrections

Freeze 前只允許以下減法／邊界修正：

1. `CORE-J01/J02`：commerce wording 改成 Human 指定／確認後的 integration boundary，不假設已有某套 capability。
2. `CORE-H01~H04`：縮成最小 5-event measurement contract；其餘 analytics governance 移 Optional。
3. `AC-H01~H03`：同步對應瘦身後的 Core，不再要求 8-event、refund/new-returning/tax-shipping policy。
4. 其他 Core / Optional / Acceptance 不擴張，不新增新功能。

## Human Gate B conclusion

**可以進 Spec Freeze。**

這輪證明 `Core / Optional / Acceptance` 分層有效降低了 Spec Bloat，但也暴露新的 Harness 風險：

> Agent 會把「量測要可用」自然擴張成「完整 analytics governance」。

因此新增 Candidate Rule：

### Minimum Observability Before Analytics Governance
第一輪只收集能回答下一個商業決策的最小資料；refund taxonomy、customer lifecycle、完整 attribution 等治理規則，等真實資料與決策需求出現後再升級。

目前只在 EXP-001 出現，先列 Candidate，不升級正式 donix Rule。
