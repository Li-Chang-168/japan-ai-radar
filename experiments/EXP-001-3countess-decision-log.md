# EXP-001｜3countess Decision Log

## D-001｜品牌定位
- Decision: 三爵定位為「質感生活選物品牌」。
- Authority: Owner
- Type: Client Truth
- Status: Approved

## D-002｜商品策略 v1
- Decision: 茶與生活選物列主力，精油／預購保留，手機殼待測。
- Authority: Owner
- Type: Client Truth
- Status: Superseded
- Superseded by: D-005 / D-006

## D-003｜Logo
- Decision: Logo 可保留，其餘網站數位表達可重新思考。
- Authority: Owner
- Type: Client Truth
- Status: Approved

## D-004｜網站目標
- Decision: 新站主要追求網站訂單增加、新客增加、生活選物形成穩定銷量。
- Authority: Owner
- Type: Client Truth
- Status: Approved

## D-005｜移除舊商品線
- Decision: 新站移除茶葉、精油、手機殼與舊預購商品線，只保留生活選物。
- Authority: Owner
- Type: Client Truth
- Decided at: 2026-08-08 19:32 Asia/Taipei
- Status: Approved

## D-006｜三條生活選物線
- Decision: 新站生活選物分為三條產品線：A 收藏生活、B Analog Everyday、C Pet Walk EDC。
- Authority: Owner
- Type: Client Truth
- Status: Approved

### A｜收藏生活
- Hero: 透明收藏展示吊掛盒
- Attach: Photocard Holder / 徽章 Holder / Acrylic Stand Case
- Target AOV: NT$690–1,090

### B｜Analog Everyday
- Hero: Traveler Journal Charm
- Attach: Bookmark Charm / 黃銅書籤 / Pen Loop
- Target AOV: NT$590–990

### C｜Pet Walk EDC
- Hero: Urban Walk Pouch
- Use case: 零食＋拾便袋＋鑰匙＋卡＋手機小物
- Attach: Leash Pouch / Poop Bag Holder / Pet Tag
- Target AOV: NT$790–1,290

## D-007｜市場驗證狀態
- Decision: 過去茶的成交紀錄不再作為新站商品優先級依據；三條新生活選物線均視為尚待市場驗證。
- Authority: donix process rule based on Owner strategy change
- Type: Experiment boundary
- Status: Approved for EXP-001

## D-008｜Working Brand Architecture
- Decision: 進入 Core Spec 時採用「一個質感生活選物品牌 × 三個生活情境」。
- Detail: 三條線共用品牌、信任、主要導向與交易骨架；差異主要存在於情境入口、collection、商品內容與後續依市場證據調整的曝光。
- Boundary: 這不是正式 slogan；共同品牌價值的最終對外表述尚未 Approved。
- Authority: Human Gate A
- Confirmed at: 2026-08-08 19:56 Asia/Taipei
- Status: Approved

## D-009｜第一條 Vertical Slice
- Decision: 第一條 Vertical Slice 選擇 B｜Analog Everyday，Hero 為 Traveler Journal Charm。
- Reason: 目前唯一可用的市場 Signal 加上較集中的紙本日常使用情境，使其適合作為第一輪完整購買路徑測試。
- Boundary: 這只是實驗優先順序，不代表已驗證主力、永久首頁主角或最終資源配置。
- Authority: Human Gate A
- Confirmed at: 2026-08-08 19:56 Asia/Taipei
- Status: Approved

## D-010｜Journal Charm Signal 邊界
- Decision: `Journal Charm 搜尋 +395%` 持續標記為 Unverified Market Signal。
- Boundary: 不得把搜尋增長等同於購買需求、台灣市場規模、可接受售價或產品市場契合。
- Authority: Human Gate A
- Status: Approved

## D-011｜No Invented Facts Correction
- Decision: 不得假設 3countess 為一人公司；後續 Spec 只要求降低不必要的重複維護負擔。
- Source: CONSULT v2 Human Gate correction.
- Authority: Human Gate A
- Status: Approved

## D-012｜Spec Layering
- Decision: 本次 Spec 強制分為 `core.md`、`optional.md`、`acceptance.md`。
- Reason: 避免 EXP-000 已發現的 Spec Bloat，並測試 Core vs Optional Spec Rule。
- Authority: Human Gate A
- Status: Approved

## D-013｜Human Gate B
- Decision: `core.md` / `optional.md` / `acceptance.md` 通過 Human Gate B，但 Freeze 前只做兩類減法修正，不重跑完整 Spec。
- Authority: Human Gate B
- Confirmed at: 2026-08-08 20:13 Asia/Taipei
- Status: Approved with correction

### Correction A｜Commerce capability wording
- 未確認前不得寫成已有既定 commerce capability。
- 統一改為「由 Human 指定並確認的 commerce capability / integration boundary」。
- `system of record`、cart / checkout contract、purchase confirmation 等在 Coding 前仍是 unresolved blocker。

### Correction B｜Minimum measurement reduction
Core 只保留第一輪 Vertical Slice 做商業判斷所需的最小事件：
1. `view_context`
2. `view_item`
3. `add_to_cart`
4. `begin_checkout`
5. `purchase`

Core 最小資料：
- product_line
- product / variant ID（適用事件）
- quantity（交易事件）
- transaction value / currency（交易事件）
- traffic source / campaign（若現有能力可取得）
- purchase unique order ID

以下降為 Optional / later measurement contract：
- `view_home`
- `select_context`
- `select_item`
- refund / cancellation reconciliation
- new vs returning customer definition
- tax / shipping / refund revenue policy
- advanced placement attribution

## D-014｜Gate B Rule Transfer
- Page Existence Rule: PASS
- Inference ≠ Requirement: PASS
- Shared Transaction Backbone: PASS
- Content-to-Commerce: PASS
- No Invented Facts: PASS WITH CORRECTION
- Core vs Optional Spec: PASS WITH CORRECTION
- Result: 4 / 6 rules already transfer across brands without major modification; the remaining 2 caught boundary/scope errors rather than failing.

## D-015｜New Candidate Rule
- Candidate: **Minimum Observability Before Analytics Governance**
- Meaning: 第一輪只蒐集能回答下一個商業決策的最小資料；完整 attribution、refund taxonomy、customer lifecycle 等治理規則，等真實資料與決策需求出現後才升級。
- Status: Candidate only; not yet donix Methodology.

## D-016｜Commerce Authority
- Decision: 3countess 新站的 Human-designated commerce authority 採用 **Zenbu 原生電商能力**；對外產品／服務語境可稱為 `donix Commerce`，但 EXP-001 實作層仍需把 Zenbu 的實際 product / variant / cart / checkout / order / purchase confirmation contract 查清楚後才能進 production transaction coding。
- Source: prior Owner decision to migrate the 3countess / donix standard e-commerce path away from WP + WooCommerce and onto Zenbu Site native commerce.
- Boundary: 這只解決「誰是 commerce authority」；不代表 cart / checkout / purchase contract 已驗證，也不得由 Agent憑平台能力線索自行補完契約。
- Authority: Owner / Human Gate production readiness
- Confirmed for EXP-001 at: 2026-08-10
- Status: Approved
