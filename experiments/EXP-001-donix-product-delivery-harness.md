---
id: EXP-001-donix-product-delivery-harness
status: backlog
pattern:
  - PAT-001-judgment-as-code
  - PAT-002-human-supervisor-agent-executor
  - PAT-003-compounding-harness
  - PAT-004-non-engineer-builder
owner: Li-Chang
start_date:
end_date:
---

# donix Product Delivery Harness｜把顧問判斷變成可重複的 Agent 交付流程

## 要驗證的問題
能否把 donix 從「每次靠長 Prompt 與即席判斷」改造成一條由規格、Agent Skills、Human Gate 與回寫機制驅動的交付流程，讓一人公司在不降低品質下減少重複思考與來回修正？

## 假設
如果先把商業判斷、品牌原則、UX / SEO / conversion criteria 與交付邊界結構化，再讓 Agent 執行研究、架構、實作與 QA，則：
1. 產出第一版可開發規格的時間可下降至少 50%。
2. 因 Agent 誤解品牌、商業目標或網站架構造成的重大返工可下降。
3. 每完成一個專案，至少能回收 1 個可重複使用的 rule / skill / checklist，形成複利。

## 最小測試
只測一個真實網站專案，不建立 SaaS、不建立 Dashboard。

### Phase 0｜Project Context
建立 repo 級：
- `AGENTS.md`：角色、禁區、商業優先順序
- `context/brand.md`
- `context/business.md`
- `context/audience.md`
- `context/offers.md`

### Phase 1｜CONSULT
Agent 產出：問題定義、客群、購買理由、商業優先級、風險、待驗證假設。

**Human Gate A**：只由人決定定位、優先順序與是否值得做。

### Phase 2｜AUDIT / SPEC
Agent 把通過的判斷轉成：
- `spec/product.md`
- `spec/site-architecture.md`
- `spec/conversion.md`
- `spec/content.md`
- `spec/acceptance-criteria.md`

**Human Gate B**：確認 IA、轉換路徑、品牌與商業邏輯。

### Phase 3｜CODING
Coding Agent 根據 spec 執行 UI / frontend / integration；禁止自行改寫已批准的商業需求。

### Phase 4｜QA
分成專門 Reviewer：
- Brand Reviewer
- UX / Conversion Reviewer
- SEO Reviewer
- Technical Reviewer

AI 處理 checklist；人只處理 trade-off 與最後驗收。

### Phase 5｜Harness Review
任務完成後回答三題：
1. 哪些事情我又重新解釋了一次？
2. 哪些 Agent 錯誤下次不應再發生？
3. 哪一個判斷值得寫成 rule / skill / checklist？

只要答案具重複性，就回寫 AGENTS.md / Skill / guideline。

## 使用場景
- [x] donix
- [x] DON ACC.
- [x] Internal

首選測試：下一個實際網站重構／新建任務；若需要低風險內部場景，可用 DON ACC. 官網前端與轉換架構作為驗證場。

## 工具
- GitHub repository
- Codex 或 Claude Code（主執行 Agent 擇一即可）
- Markdown specs
- Git / PR
- 現有 deployment workflow

第一輪不要同時導入多模型 orchestration；先驗證 Harness 本身是否有效。

## 成功指標
- 從原始需求到 approved development spec 的工時下降 ≥ 50%。
- Human Gate 前後重大方向修改 ≤ 2 次。
- Coding 後因「需求理解錯誤」造成的大返工 = 0。
- 至少產生 3 個可重複 rules / skills / checklists。
- 第二次相似任務能直接重用其中至少 2 個資產。
- 最終成果仍由人判定符合品牌、商業與 UX 要求。

## 時間 / 成本上限
- Harness 初始化：最多 2 小時。
- 每次任務結束 Harness Review：最多 10 分鐘。
- 第一輪禁止開發自訂管理 UI、資料庫、Crawler 或 SaaS。

## 停止條件
若出現任一條件，停止擴充 Harness：
- 維護規則所花時間高於節省的重複溝通時間。
- 連續 2 次任務都沒有可重用的新知識。
- Agent 因過多規則而明顯降低判斷品質或頻繁衝突。
- 流程讓簡單任務變得比直接執行更慢。

## 結果
待執行。

## 結論
- [ ] Adopt
- [ ] Iterate
- [ ] Reject

## 可沉澱的方法論
若驗證成功，將形成 donix 的「AI-native Brand Digital Delivery System」：
Human Judgment → Spec → Agent Execution → AI Review → Human Gate → Harness Learning。
