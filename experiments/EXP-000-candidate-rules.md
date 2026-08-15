# EXP-000 Candidate Rules

> 來源：EXP-000 Harness Replay Test。這些規則已在單一去識別化 Replay 中展現價值，但尚未經第二個不同類型專案驗證，因此目前仍是 candidate rules，不直接升格為正式 methodology。

## 1. Page Existence Rule

每個頁面／功能都必須回答：
- 服務誰？
- 解決什麼問題？
- 推動什麼下一步？
- 如果刪除會失去什麼？

回答不出來就不新增。

## 2. Inference ≠ Requirement Rule

合理推論、最佳實務、未知平台能力，不得直接升格為：
- 固定 scope
- 必做技術架構
- 上線 blocker

必須明確標記為 inference / optional / unresolved。

## 3. Shared Transaction Backbone Rule

不同 customer journey 優先透過：
- 入口
- 資訊排序
- 內容策展

來區分，不因 journey 不同就複製商品、資料或交易系統。

## 4. Content-to-Commerce Rule

SEO、指南、教育內容必須：
1. 解決真實問題；
2. 有清楚下一步；
3. 自然連回相關商品、服務或轉換節點。

不為文章量建立內容。

## 5. No Invented Facts Rule

Agent 可以要求資料欄位完整，但不得為了規格、版面或文案完整而編造不存在／不適用的商品、服務、營運或平台事實。

## 6. Core vs Optional Spec Rule

Spec 必須至少分成：
- Core Requirements
- Optional / Platform-dependent Checks
- Open Assumptions

只有真正影響商業目標、使用者核心任務、品牌邊界、法規／風險或交易完成的項目才應成為 Core。

## 驗證狀態

- Single sanitized replay：已驗證一次
- 第二個不同類型專案：未驗證
- 正式 methodology：未採用

至少需在另一個不同類型專案再次驗證，才能考慮升級。
