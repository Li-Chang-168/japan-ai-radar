# EXP-000｜Codex Execution Prompt

> 使用前提：Codex 只能看到 Replay 工作 repo / folder，不得連接 Japan AI Radar 的 Ground Truth 檔。

## Round A｜Consult Replay

你正在執行 EXP-000 Harness Replay Test。

請先完整閱讀：
- `AGENTS.md`
- `context/brand.md`
- `context/business.md`
- `context/audience.md`
- `context/constraints.md`

本回合禁止寫程式、禁止設計 UI 畫面、禁止建立未要求的系統。

你的任務不是討好需求，而是根據既有 context 做顧問判斷。

請產出 `output/consult.md`，必須包含：

1. 真正要解決的商業問題
2. 網站現階段最重要的 3 個優先級
3. 主要客群與其決策障礙
4. 核心購買 / 行動理由
5. 建議的主要轉換路徑
6. 必須避免的方向
7. 已知事實
8. 合理推論
9. 尚未驗證假設
10. 最多 5 個真正會阻礙下一步的風險或缺口

規則：
- 不要把一般網站最佳實務當成這個品牌的答案。
- 不要為完整而增加功能。
- 不要自行改變已知平台 / 技術邊界。
- 不要因資訊不足就停止；可以標記假設，但不可假裝確定。
- 如果 context 內有矛盾，請指出，不要自行選擇一邊。

完成後停止，不要進入 Spec。

---

## Round B｜Spec Replay

只有 Human Gate 通過 Round A 後才執行。

請閱讀：
- `AGENTS.md`
- `context/*`
- 已批准的 `output/consult.md`

產出 `output/spec.md`。

Spec 只描述「要做成什麼」與「如何判定完成」，不寫 implementation code。

必須包含：

1. Project objective
2. Target users / audience
3. Value proposition
4. Information architecture
5. Core page responsibilities
6. Primary conversion paths
7. Content / tone constraints
8. UX principles
9. SEO requirements
10. Technical constraints
11. Acceptance criteria
12. Non-goals
13. Open assumptions / unresolved questions

要求：
- 每個頁面必須有存在理由，不可只因常見網站都有就加入。
- Acceptance criteria 必須可檢查。
- Non-goals 必須明確，避免 scope creep。
- 不新增 context 中不存在、且沒有商業理由支持的功能。
- 不要建立 dashboard、會員、AI 功能、自動化等額外系統，除非 context 已明確要求。

完成後停止。

---

## 禁止事項

整個 EXP-000 不得：
- 讀取 Ground Truth
- 搜尋舊版最終 Vibe Coding Prompt 當答案
- 寫 frontend code
- 建立 Skills
- 修改 AGENTS.md
- 自動把本次觀察提升為永久規則
- 使用多 Agent / 多模型互評

這是一個 Replay Test，不是產品開發任務。
