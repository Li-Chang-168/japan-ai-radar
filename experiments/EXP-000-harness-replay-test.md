---
id: EXP-000-harness-replay-test
status: active
pattern:
  - PAT-001-judgment-as-code
  - PAT-002-human-supervisor-agent-executor
owner: Li-Chang
start_date: 2026-08-08
end_date:
---

# EXP-000｜Harness Replay Test

## 目的
在不進入正式 Coding、不建立完整 Harness 的前提下，用一個「已經有最終決策答案」的既有專案回放，驗證：

> 結構化 Project Context + Judgment Rules + Spec 是否比「每次重新解釋 + 長 Vibe Coding Prompt」更穩定、更省重複思考，且能形成可重用資產。

本實驗不是驗證 AI 能不能做網站，而是驗證 donix 是否值得把「人的判斷」結構化為 Agent-readable delivery system。

---

## Replay 專案

首選：懂飾 DON ACC. 官網 AI-native 重構。

### 為什麼用懂飾
- 已有明確品牌定位與禁區。
- 已做過網站架構、商品分類、UX、轉換、SEO 與 Vibe Coding Prompt 討論。
- 已知若干已接受 / 已拒絕方向，可作 Ground Truth。
- 使用者本人是最終品牌與商業判斷者，不需要額外找客戶確認。

---

## 本次只測的核心鏈條

```text
Raw Context
  ↓
Structured Context
  ↓
Judgment Rules
  ↓
Consult Output
  ↓
Human Gate
  ↓
Development Spec
  ↓
Replay Score
```

### 明確排除
本次不做：
- Frontend coding
- Deployment
- Multi-Agent orchestration
- Multi-model comparison
- 自動修改 AGENTS.md
- 自動生成 Skills
- Database / Dashboard / Crawler
- 4-role AI review pipeline

---

## 90 分鐘時間盒

### T+00–10｜建立 Ground Truth（10 分）
不要先讓 Agent 看完整答案。

由 Human 建立 `ground-truth.md`，只記錄已經確定的最終判斷，至少包含：

1. 品牌核心定位
2. 網站主要商業目標
3. 主要客群
4. 購買 / 行動理由
5. 必要頁面與主要轉換路徑
6. 已確定不採用的方向
7. 品牌 / 文案 / UX 禁區
8. 技術與平台邊界

Ground Truth 是最後評分基準，不提供給 Replay Agent。

### T+10–30｜建立 Minimum Context Pack（20 分）
只整理 Agent 真正需要的背景，不追求完整知識庫。

建立：

```text
replay/
├── AGENTS.md
└── context/
    ├── brand.md
    ├── business.md
    ├── audience.md
    └── constraints.md
```

限制：
- 每個 context 檔原則上 ≤ 500 字。
- AGENTS.md 原則上 ≤ 800 字。
- 只寫已知事實、明確規則、優先順序。
- 不把既有最終網站架構答案直接塞進 context。

### T+30–45｜Replay A：Consult（15 分）
給單一 Agent：AGENTS.md + context/*。

任務：
1. 定義真正要解決的商業問題。
2. 排出網站優先級。
3. 提出目標客群的理解。
4. 建議主要轉換路徑。
5. 指出風險、矛盾與尚未驗證假設。
6. 明確列出「不應該做什麼」。

輸出：`replay/output/consult.md`

Human 此時只做 Gate，不直接幫它重寫答案。

記錄：
- 哪些地方需要補充解釋？
- 哪些判斷與 Ground Truth 明顯衝突？
- 哪些新洞察值得保留？

### T+45–65｜Replay B：Spec（20 分）
只把 Human Gate 通過的 Consult 結論交給同一 Agent。

產出：

```text
replay/output/spec.md
```

最小 Spec 必須包含：
- Project objective
- User / audience
- Value proposition
- Information architecture
- Core page responsibilities
- Primary conversion paths
- Content / tone constraints
- UX principles
- SEO requirements
- Technical constraints
- Acceptance criteria
- Non-goals

本階段不寫 implementation code。

### T+65–80｜Blind Compare（15 分）
Human 以 `ground-truth.md` 對照 Consult + Spec。

不得因為「AI 寫得很完整」就給高分。

使用 EXP-000 Scorecard 評估：
- Ground Truth alignment
- Business judgment
- Brand alignment
- Conversion / UX logic
- Completeness without bloat
- Need for re-explanation
- Reusable knowledge discovered
- Process overhead

### T+80–90｜Harness Review（10 分）
只回答：

1. 哪些事情我又重新解釋了一次？
2. 哪些 Agent 錯誤下次不應再發生？
3. 哪些判斷具有跨專案可重用價值？
4. 哪些內容只屬於懂飾，不應升級成 donix rule？
5. 這套流程比原本直接寫 Vibe Coding Prompt 更簡單還是更複雜？

只把具有重複性的項目列入 `candidate-rules.md`，不自動寫回正式 Harness。

---

## 成功條件

### 必須條件
以下三項全部成立才可進 EXP-001：

1. Spec 品質不低於既有最終決策。
2. 至少產生 3 個可重用 rule / checklist / context pattern。
3. 整個 Harness 沒有造成明顯高於收益的維護負擔。

### 量化參考
- Ground Truth alignment ≥ 80%。
- 重大品牌 / 商業方向錯誤 ≤ 1 個。
- Human 額外重新解釋 ≤ 3 次。
- reusable assets ≥ 3 個。
- context + rule 初始化 ≤ 30 分鐘。
- 全部 Replay ≤ 90 分鐘。

---

## 停止條件

任一成立即停止擴充 Harness：

- Context Pack 建立超過 30 分鐘仍無法完成。
- 為了讓 Agent 正確工作，需要把完整既有答案直接餵回去。
- Agent 仍反覆誤解核心品牌 / 商業方向。
- Spec 只是把 Context 換句話說，沒有產生可用結構。
- 流程比直接建立 Vibe Coding Prompt 更慢、且沒有額外 reusable knowledge。
- 為了一個簡單專案需要大量 Rules / Skills 才能工作。

---

## 決策規則

### ADOPT → 啟動 EXP-001
若必須條件全部成立，而且 Replay 明顯降低重複解釋。

### ITERATE → 再跑一次 EXP-000B
若核心方向有效，但 context / rules 過多或格式需要簡化。第二次只允許減法，不允許增加複雜架構。

### REJECT
若沒有比現有「顧問判斷 + 高品質 Prompt」產生明顯優勢。

Reject 不代表 Agentic Development 無效，只代表完整 Harness 不適合目前 donix 的複雜度與規模。

---

## 本實驗真正要驗證的問題

不是：
> Agent 能不能產生一份網站規格？

而是：
> donix 最有價值的品牌、商業、UX 判斷，能否以低維護成本被結構化、重用，並持續提升下一個專案的 AI 執行品質？
