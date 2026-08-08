# Japan AI Radar

日本 AI-native／AI駆動開發情報雷達。目的不是蒐集 AI 新聞，而是持續找出「日本已經開始實作、台灣仍少見、值得 donix／一人公司驗證」的高價值訊號，並把訊號轉成可測試的方法論與工作流程。

## 核心流程

```text
Sources → Candidate Signals → Signal Score → Signals ≥ 8 → Pattern → Experiment → Result → Adopt / Reject → donix Methodology
```

## Signal Score

每個候選訊號 5 個維度，各 0–2 分：新穎度、實務性、可複製性、商業價值、長期價值。

- 0–5：忽略
- 6–7：觀察，不進主雷達
- 8–10：高訊號，建立 Signal
- 已知事件若沒有實質新進展，不重複建立 Signal

## 研究主題

Claude Code、Codex、Cursor、MCP、Agent Skills、Agent Harness、Spec Driven Development、Multi-Agent、AI-native、非工程師 AI Builder、企業 AI 導入、AI 工作流程自動化、Agentic Software Development、AI駆動開発。

## 優先來源

CyberAgent、Mercari、Rakuten、LayerX、Sakana AI、OpenAI Japan、Anthropic Japan、Microsoft Japan、GitHub Japan；以及 Zenn、Qiita、note、Speaker Deck、connpass。

## Repo 使用規則

1. 不把一般產品更新當成 Signal。
2. Signal 必須有原始來源。
3. 優先記錄實際 workflow、數字、組織設計、失敗案例、架構。
4. 不因 AI 新潮而實驗；實驗必須回答商業或營運問題。
5. donix 採用的方法必須能標準化、模組化或降低交付成本。

## 最小維運節奏

- 每日：只處理 8–10 分高訊號
- 每週：把 Signals 合併成 Patterns
- 每月：挑 1–2 個 Experiment
- 每季：整理 adopted methods，更新 donix 方法論

## MVP 停止條件

若連續 4 週高訊號不足 5 個，或沒有任何訊號導出值得測試的 Experiment，或 Experiment 與 donix / 一人公司沒有實際關聯，則停止擴充系統，不開發 Dashboard / Collector。
