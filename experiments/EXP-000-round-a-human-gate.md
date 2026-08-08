# EXP-000｜Round A Human Gate

用途：Codex 完成 `output/consult.md` 後，由 Human 進行 Gate。不要讓同一個 Agent 自評。

## Gate 規則

每個重大判斷只標記三種：

- `APPROVE`：方向可直接進 Spec。
- `CORRECT`：Agent 對既有品牌／商業事實理解錯誤，需要 Human 補正。
- `UNKNOWN`：資訊本來就沒有提供，不能算 Agent 錯誤；標記為未驗證假設或待確認。

Human 不要把整份 consult 重寫成自己的版本，只記錄最小必要補正，避免污染 Re-explanation 指標。

---

## 1. 真正要解決的商業問題
- Gate：APPROVE / CORRECT / UNKNOWN
- 註記：

## 2. 三個最高優先級
- Gate：APPROVE / CORRECT / UNKNOWN
- 註記：

## 3. 客群與決策障礙
- Gate：APPROVE / CORRECT / UNKNOWN
- 註記：

## 4. 核心購買／行動理由
- Gate：APPROVE / CORRECT / UNKNOWN
- 註記：

## 5. 主要轉換路徑
- Gate：APPROVE / CORRECT / UNKNOWN
- 註記：

## 6. 必須避免的方向
- Gate：APPROVE / CORRECT / UNKNOWN
- 註記：

## 7. Known Facts / Inferences / Assumptions 分離
- Gate：APPROVE / CORRECT / UNKNOWN
- 是否把假設寫成事實：Yes / No
- 註記：

## 8. 風險與缺口
- Gate：APPROVE / CORRECT / UNKNOWN
- 是否真的阻礙下一步：Yes / No
- 註記：

---

# Critical Error Check

- [ ] 誤解品牌定位
- [ ] 誤解網站主要商業目標
- [ ] 提出已明確禁止的策略
- [ ] 轉換路徑與購買情境矛盾
- [ ] 自行改變技術／平台邊界
- [ ] 將尚未驗證假設寫成事實

Critical error count: ____

# Re-explanation Log

只記錄 Human 必須重新解釋「原本 context 已經存在」的資訊。

1. 
2. 
3. 

Total: ____

> 若資訊根本沒有提供，應標 `UNKNOWN`，不算 Re-explanation。

# New Insight Log

Agent 若提出 Ground Truth 沒有、但 Human 認為值得研究的新洞察，記在這裡；不得回頭修改 Ground Truth。

1. 
2. 
3. 

# Round A Decision

- [ ] PASS → 可執行 Round B Spec
- [ ] PASS WITH CORRECTION → Human 補入最小修正後再執行 Round B
- [ ] FAIL → 不進 Round B，先分析 Context / Rules 為何失效

## Pass 建議門檻

- Critical errors ≤ 1
- Re-explanation ≤ 3
- 核心品牌、商業問題、客群、轉換方向大致正確
- 未把重大假設當成既定事實

## Human correction for Round B

只在 `PASS WITH CORRECTION` 時填寫，最多 5 點：

1. 
2. 
3. 
4. 
5. 
