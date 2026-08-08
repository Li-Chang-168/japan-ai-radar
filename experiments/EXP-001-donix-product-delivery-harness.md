---
id: EXP-001-donix-product-delivery-harness
status: active
pattern:
  - PAT-001-judgment-as-code
  - PAT-002-human-supervisor-agent-executor
  - PAT-003-compounding-harness
  - PAT-004-non-engineer-builder
owner: Li-Chang
start_date: 2026-08-08
end_date:
client_case: 3countess
client_truth_version: v2
---

# EXP-001｜donix Product Delivery Harness × 3countess

## 目的
在一個非 DON ACC.、且沒有既知 Ground Truth 的真實品牌案中，驗證 EXP-000 已通過的核心鏈條能否延伸到真正交付：

> Client Truth → Structured Context → donix Judgment → Human Gate → Core Spec → Coding → QA → Human Gate → Harness Review

本次不是再驗證 Agent 能不能寫 Spec，而是驗證 donix 是否能把別人的商業資訊轉成 Agent-readable delivery system，並完成一條真實可用的網站 Vertical Slice。

## Client case｜3countess v2

品牌：3countess / 三爵

Owner 最新決策：
- 品牌定位：**質感生活選物品牌**。
- 新站移除茶葉、精油、手機殼與舊預購商品線。
- 新站只保留生活選物，分成三條產品線：
  1. 收藏生活
  2. Analog Everyday
  3. Pet Walk EDC
- 過去茶曾有成交，但已退出新商品策略，因此只保留為歷史證據，不影響新站 IA / 商品優先級。
- 三條新產品線目前都尚未有實際成交證據。
- 網站角色：看懂品牌與商品、建立信任、直接下單。
- 現站主要問題：網站沒有帶來訂單、商品很亂、不知道從哪裡買。
- 一年後前三個結果：網站訂單增加、新客變多、生活選物開始有穩定銷量。

有效 Client Truth：`EXP-001-3countess-client-truth-v2.md`。
舊版 v1 保留作決策歷史，但不得再餵給 Agent。

## 三條產品線

### A｜收藏生活
- Hero：透明收藏展示吊掛盒
- Attach：Photocard Holder / 徽章 Holder / Acrylic Stand Case
- Target AOV：NT$690–1,090

### B｜Analog Everyday
- Hero：Traveler Journal Charm
- Attach：Bookmark Charm / 黃銅書籤 / Pen Loop
- Target AOV：NT$590–990

### C｜Pet Walk EDC
- Hero：Urban Walk Pouch
- Use case：零食＋拾便袋＋鑰匙＋卡＋手機小物
- Attach：Leash Pouch / Poop Bag Holder / Pet Tag
- Target AOV：NT$790–1,290

`Journal Charm +395%` 與台灣市場尚未完全商品化的觀察，獨立記錄於 `EXP-001-3countess-market-signals.md`，目前屬未驗證 Signal，不得當成 Client Truth。

## EXP-000 transfer test

本次優先測試下列 6 個 Candidate Rules 是否可跨品牌重用：

1. Page Existence Rule
2. Inference ≠ Requirement Rule
3. Shared Transaction Backbone Rule
4. Content-to-Commerce Rule
5. No Invented Facts Rule
6. Core vs Optional Spec Rule

成功條件之一：至少 4 / 6 條不需重大修改即可直接重用。

## Phase 0｜Client Truth + Current Site Audit

已完成：
- Owner Interview / Client Truth v1
- Owner Strategy Update / Client Truth v2
- Public current-site audit
- Decision Log

Human authority 分工：
- Owner = Fact Authority：品牌、商品、營運、履約與實際商業事實。
- donix = Judgment Authority：品牌架構、IA、conversion、UX、scope 與 digital delivery 判斷。

不得用網站現況取代 Owner Truth，也不得把 donix 推論寫成客戶事實。

## Phase 1｜Minimum Context Pack

建立 3countess 專案工作區：

```text
AGENTS.md
context/
  brand.md
  business.md
  audience.md
  catalog.md
  constraints.md
audit/
  current-site.md
research/
  market-signals.md
decisions/
  decision-log.md
```

Context 只放已知事實、已批准方向、限制與必要 Audit；不預先寫最終 IA。

## Phase 2｜CONSULT

Agent 必須回答：
- 三爵現在真正要解決的商業問題。
- 三條生活選物線如何被一個 Master Brand 統合，而不變成三個互不相干的小商店。
- 三條線的共同價值與各自購買情境應如何分工。
- 現階段最重要的 3 個網站優先級。
- 新客第一次進站如何理解品牌、辨認三條線、建立信任並採取購買行動。
- 三條線應共用哪些網站／交易骨架，哪些差異只應存在於入口、內容與商品呈現。
- 哪些現站元素只是 legacy，不應自動保留。
- 哪些是 Known Facts / Inferences / Unverified Assumptions。
- 哪些事情目前不應該做。

**Human Gate A**：Owner 只校正 Fact；donix 決定 Judgment / Priority / Scope。

## Phase 3｜SPEC

為避免 EXP-000 發現的 Spec Bloat，本次 Spec 強制分層：

```text
spec/
  core.md
  optional.md
  acceptance.md
```

### Core
只放不做就無法正確交付的品牌、IA、頁面責任、conversion、content hierarchy 與 commerce boundary。

### Optional
SEO 進階項目、platform-dependent capability、enhancement 等非 blocker 檢查，不得與 Core 同權重。

### Acceptance
只定義可觀察、可驗收的完成條件。

**Human Gate B / Spec Freeze**：通過後 Coding Agent 不得自行改寫商業需求；只能提出風險或請求 Human decision。

## Phase 4｜CODING Vertical Slice

第一輪禁止整站一次重做。

只完成一條真實購買 Vertical Slice：

```text
Header / Navigation
→ Homepage
→ One Product Line / Collection
→ Hero Product Detail
→ Add-to-cart / commerce boundary
```

Primary line 在 Human Gate A / B 後決定，不因未驗證市場 Signal 自動指定。

Coding Agent 依 Frozen Core Spec 執行 UI / frontend / integration；不得自行新增會員、AI 導購、推薦、dashboard、crawler 或 backend。

## Phase 5｜QA

第一輪仍使用單一主要 Agent + checklist，不建立四 Reviewer Multi-Agent。

AI 處理：
- Spec compliance
- build / lint / type
- responsive
- broken states
- core SEO implementation
- commerce boundary
- acceptance checklist

Human 處理：
- 品牌感
- 商業邏輯
- 資訊層級
- UX trade-off
- 是否違反 Frozen Spec

## Phase 6｜Harness Review

完成 Vertical Slice 後回答：
1. 哪些資訊又需要 Human 重新解釋？
2. 哪些 Agent 錯誤下次不應再發生？
3. EXP-000 的 6 條 rules 有幾條真正可直接重用？
4. 哪些 3countess-specific knowledge 不應升級為 donix rule？
5. 是否產生新的跨品牌 rule / checklist？
6. Harness 是否真的讓 Human 時間集中在 Judgment，而不是重寫 Agent 產出？

## 成功指標

- Owner 已提供事實被 Agent 誤解：≤ 2 次。
- Gate B 後重大品牌 / 商業 / IA 改向：≤ 1 次。
- Coding 後因需求理解錯誤造成的大返工：0 次。
- Vertical Slice Core Acceptance 通過率：≥ 90%。
- EXP-000 Candidate Rules 可直接重用：≥ 4 / 6。
- 新 reusable rule / checklist：≥ 2 個。
- Human 主要工時集中於 judgment / trade-off，而不是重寫 Agent 成果。
- 不引進 Multi-Agent、Agent Memory、自動 Skill generation 等額外複雜度。

## 成本 / 時間上限

- Client Truth + Context Pack：≤ 90 分鐘。
- Consult + Human Gate：≤ 60 分鐘。
- Core Spec + Human Gate：≤ 90 分鐘。
- Harness Review：≤ 15 分鐘。
- Coding 只做一條 Vertical Slice，不以整站完成作為本次成功必要條件。

## Stop Conditions

任一成立即停止擴充：
- 為了讓 Agent 理解三爵，需要反覆把完整答案餵回去。
- Spec 再度膨脹到 Core / Optional 無法清楚區分。
- Gate B 後仍頻繁改變商業方向。
- Coding Agent 因需求理解錯誤產生大規模返工。
- Rules 維護成本高於節省的溝通成本。
- 為完成 Vertical Slice 被迫導入 Multi-Agent / 自動 memory / 自訂 agent platform。

## 結果
待執行。

## 結論
- [ ] Adopt
- [ ] Iterate
- [ ] Reject

## 若成功可沉澱的方法論候選

**donix AI-native Brand Digital Delivery System**

Client Truth → Human Judgment → Structured Context → Core Spec → Agent Execution → Checklist QA → Human Gate → Harness Learning

> EXP-001 成功仍只代表方法論 Candidate；需至少再經一個不同類型品牌 / 商業模式驗證後，才升級為正式 donix Methodology。
