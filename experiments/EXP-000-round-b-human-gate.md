# EXP-000｜Round B Human Gate

Source: uploaded `spec.md` produced by Codex Round B.

## Decision

**PASS — 但帶一個明確風險：Spec 開始出現完整性膨脹。**

## Core checks

### Ground Truth alignment
- Gate: APPROVE
- 說明：品牌定位、商業目標、自用／送禮、商品頁成交角色、非玄學、SEO／流量承接、技術邊界均與 frozen Ground Truth 一致。

### IA 是否有商業理由
- Gate: APPROVE
- 說明：首頁、商品、集合、送禮、指南、關於、售後都對應明確使用者任務／商業理由；Exact IA 仍是由 context 推導，不是照抄 Ground Truth。

### 是否把推論升格成 requirement
- Gate: APPROVE
- 說明：核心商品集中、歷史數據、送禮履約、平台 SEO／tracking／redirect 能力均保留為推論或 unresolved question，沒有強制成上線 blocker。

### 是否偷加 scope
- Gate: PASS WITH CAUTION
- 沒有新增被明確禁止的會員、AI 導購、dashboard、crawler、backend、multi-agent 等。
- 但 Acceptance Criteria 與 SEO / accessibility / analytics 條目偏完整，開始接近 production checklist，而非最小 Spec。

### Acceptance Criteria
- Gate: APPROVE
- 多數條件可觀察或驗收，且有明確 non-goals。

## Critical Error Check
- [ ] 誤解品牌定位
- [ ] 誤解網站主要商業目標
- [ ] 提出已明確禁止的策略
- [ ] 轉換路徑與購買情境矛盾
- [ ] 自行改變技術／平台邊界
- [ ] 將尚未驗證假設寫成事實

**Critical error count: 0**

## Re-explanation

Round B 未出現需要 Human 重新解釋既有 context 的錯誤。

**Re-explanation count: 0**

## Provisional Scorecard

| 維度 | Score | 判斷 |
|---|---:|---|
| Ground Truth alignment | 2/2 | 核心決策高度一致 |
| Business judgment | 2/2 | 商業優先於功能／技術 |
| Brand alignment | 2/2 | 品牌差異與禁區被保留 |
| Conversion / UX logic | 2/2 | 路徑清楚，支援理解、信任、成交 |
| Completeness without bloat | 1/2 | 品質高，但開始過度完整 |
| Need for re-explanation | 2/2 | 0 次 |
| Reusable knowledge | 2/2 | 已出現 ≥3 個可跨專案規則 |
| Process overhead | TBD | 需 Human 以實際時間／感受補判 |

**可評部分：13/14。最終總分區間：13–15/16。**

## Candidate reusable assets

1. **Page Existence Rule**  
   每個頁面／功能都必須回答：服務誰、解決什麼問題、推動什麼下一步、若刪除會失去什麼；沒有明確理由就不新增。

2. **Inference ≠ Requirement Rule**  
   合理策略推論與平台未知能力，不得直接升格為固定 scope、技術架構或上線 blocker。

3. **Shared Transaction Backbone Rule**  
   不同購買情境優先透過入口、資訊排序與內容策展區分；不要因 journey 不同就複製商品／交易系統。

4. **Content-to-Commerce Rule**  
   SEO／指南內容必須解決真實問題並自然接回下一個相關商品／集合；不為文章量而建立內容。

5. **No Invented Product Facts Rule**  
   結構可以要求欄位一致，但不存在／不適用的商品事實不可為了版面完整而編造。

## Main risk discovered

**Spec Bloat**：Agent 在有清楚 context 後，很容易把合理最佳實務全部寫進規格。即使每一條都「對」，總體仍可能增加閱讀、維護與執行成本。

因此若進 EXP-001，應增加一條 Harness rule：

> Spec 必須分成 `Core Requirements` 與 `Optional / Platform-dependent Checks`；非阻斷性的最佳實務不得與核心需求同權重。

## Gate conclusion

Round B 可以視為通過。EXP-000 是否 ADOPT 尚不能只靠此結果決定；還缺最後的 `Process overhead` 判定與 Harness Review。
