---
id: EXP-000-harness-replay-test
status: completed
result: adopt
score: 15/16
pattern:
  - PAT-001-judgment-as-code
  - PAT-002-human-supervisor-agent-executor
owner: Li-Chang
start_date: 2026-08-08
end_date: 2026-08-08
visibility: public
---

# EXP-000｜Harness Replay Test

## 要驗證的問題

> 高價值的品牌、商業與 UX 判斷，能否以低維護成本被結構化、重用，並提升下一個專案的 AI 執行品質？

比較的不是 AI 能不能寫 Spec，而是：

`Structured Context + Judgment Rules + Human Gate + Spec`

是否明顯優於：

`重複解釋 + 長 Vibe Coding Prompt`

## Replay 專案

本公開版本只保留經過去識別化的 replay 結構與結果。原始組織、品牌、客戶與商業 ground truth 不屬於 public repository。

Replay 使用實驗開始前已存在的最終判斷建立 Human-only Frozen Ground Truth；Replay Agent 只能看到 Minimum Context Pack，不得讀 Ground Truth 或既有最終答案。

## 測試鏈條

```text
Frozen Ground Truth (Human-only)
          │
          └──── 隔離

AGENTS.md + Minimum Context Pack
          ↓
Consult Replay
          ↓
Human Gate A
          ↓
Spec Replay
          ↓
Human Gate B / Blind Compare
          ↓
Harness Review
```

## 明確排除

本次沒有測試：
- Frontend coding
- Deployment
- Multi-Agent orchestration
- Multi-model comparison
- 自動修改 AGENTS.md
- 自動生成 Skills
- Agent memory
- Dashboard / Crawler / Database

## 公開實驗資料

- Human-only template：`EXP-000-ground-truth-template.md`
- Codex execution prompt：`EXP-000-codex-execution-prompt.md`
- Final score：`EXP-000-scorecard.md`
- Candidate rules：`EXP-000-candidate-rules.md`

Private ground truth、組織特定判斷與原始案例資料不保存在 public repository。

## 結果

**Final Score：15/16**

- Ground Truth alignment：2/2
- Business judgment：2/2
- Brand alignment：2/2
- Conversion / UX logic：2/2
- Completeness without bloat：1/2
- Need for re-explanation：2/2
- Reusable knowledge：2/2
- Process overhead：2/2（Human：明顯值得）

Critical Error：**0**  
Re-explanation：**0**

## 成功條件判定

1. Spec 品質不低於既有最終決策：**PASS**
2. 至少 3 個 reusable assets：**PASS，辨識出 6 個 candidate rules**
3. 維護成本沒有高於收益：**PASS，Human 評為 2/2「明顯值得」**

## 最重要的正向發現

1. Minimum Context Pack 足以讓 Agent 重建核心品牌與商業判斷，不需要餵最終答案。
2. Human 可以從「反覆重寫」退到 approve / correct / trade-off Gate。
3. Spec 能比單一長 Prompt 更清楚管理 known facts、inferences、unknowns、non-goals 與 acceptance criteria。
4. Project knowledge 應該自足，不依賴聊天記憶、個人化指令或「之前聊過」。

## 最重要的風險

### Spec Bloat

Agent 容易把所有合理最佳實務都加入規格。即使每條都正確，仍可能提高閱讀、維護與執行成本。

因此下一階段新增保護規則：

> Spec 必須分成 `Core Requirements`、`Optional / Platform-dependent Checks`、`Open Assumptions`；非阻斷性的最佳實務不得與核心需求同權重。

## 結論

- [x] **Adopt**
- [ ] Iterate
- [ ] Reject

**允許進入下一階段的 Product Delivery Harness experiment。**

但此結果只驗證到 Spec 層，不得直接宣稱完整 AI-native delivery harness 已成熟。下一階段必須另行驗證 `Approved Spec → Coding → QA → Human Gate → Harness Review`。
