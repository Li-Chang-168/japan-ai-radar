# EXP-000 Scorecard｜Harness Replay Test

## Final Score

| 維度 | Score | 結果 |
|---|---:|---|
| Ground Truth alignment | 2/2 | 核心決策高度一致 |
| Business judgment | 2/2 | 能抓到真正問題與優先級 |
| Brand alignment | 2/2 | 品牌差異與禁區被穩定保留 |
| Conversion / UX logic | 2/2 | 清楚支援理解、信任、選購與成交 |
| Completeness without bloat | 1/2 | 品質高，但 Spec 開始有完整性膨脹 |
| Need for re-explanation | 2/2 | Round A / B 均為 0 次 |
| Reusable knowledge | 2/2 | 找到至少 5 個候選可重用規則 |
| Process overhead | 2/2 | Human 判定「明顯值得」 |

**Final Score：15/16**

## Critical Errors

- [ ] 錯誤理解品牌定位
- [ ] 錯誤理解主要商業目標
- [ ] 提出已明確禁止的策略
- [ ] 轉換路徑與客群需求不一致
- [ ] 自行改變已知技術 / 平台邊界
- [ ] 將尚未驗證假設寫成既定事實

**Critical errors count: 0**

## Re-explanation Log

Human 在 Round A 與 Round B 均不需要重新解釋已存在於 context 的核心品牌／商業資訊。

**Total: 0**

## Candidate Reusable Assets

1. **Page Existence Rule**
   - 每個頁面／功能都必須能說明：服務誰、解決什麼問題、推動什麼下一步、刪除會失去什麼。
   - 可跨專案，因為它是 scope / IA 的通用判斷原則。

2. **Inference ≠ Requirement Rule**
   - 合理推論與未知平台能力不得直接升格成固定 scope、架構或上線 blocker。
   - 可跨專案，能防止 Agent 把「可能合理」寫成「必須做」。

3. **Shared Transaction Backbone Rule**
   - 不同 customer journey 優先透過入口、資訊排序與內容策展區分，不因 journey 不同就複製交易系統。
   - 可跨電商與服務型專案。

4. **Content-to-Commerce Rule**
   - SEO／指南內容必須解決真實問題並自然接回下一個相關商品、服務或轉換節點。
   - 可用於 donix 的品牌網站與電商交付。

5. **No Invented Facts Rule**
   - 規格可要求資料結構完整，但不存在／不適用的產品或商業事實不可為了版面完整而編造。
   - 可跨所有 Agent-driven delivery。

6. **Core vs Optional Spec Rule**
   - Spec 必須區分 Core Requirements 與 Optional / Platform-dependent Checks；非阻斷性的最佳實務不得與核心需求同權重。
   - 來源：本次最主要風險 Spec Bloat。

## Final Decision

- [x] **ADOPT → 進 EXP-001**
- [ ] ITERATE → EXP-000B，只簡化、不加架構
- [ ] REJECT → 回到高品質 Prompt workflow

### Decision rationale

三個必要 Gate 全部成立：

1. Spec 品質不低於既有最終決策，且 Ground Truth alignment 高。
2. 產生 ≥3 個跨專案可重用 rules；實際辨識出 6 個候選規則。
3. Human 將 Process Overhead 評為 2/2「明顯值得」，且 Round A / B re-explanation = 0。

因此結論不是「完整 Harness 已被驗證」，而是：

> **結構化 Project Context + Judgment Rules + Human Gate + Spec 值得進一步投入正式交付實驗。**

## 最重要的新發現

### 正向
- Minimum Context Pack 已足以重建核心品牌／商業判斷，不需要把最終答案塞給 Agent。
- Human Gate 可以把人從「重寫答案」移到「批准／修正／判斷 trade-off」。
- Spec 對 Agent execution 的價值明顯高於只交付一段長 Vibe Coding Prompt。

### 風險
- **Spec Bloat**：Agent 會把合理最佳實務持續加入規格，即使每一條都合理，總體仍可能增加閱讀、維護與執行成本。

## 下一次絕對不要再增加的複雜度

EXP-001 第一輪仍禁止：
- Multi-Agent orchestration
- Multi-model comparison
- 自動修改 AGENTS.md
- 自動 Skill generation
- Agent memory system
- Dashboard / crawler / database

下一階段只新增必要的 **Coding → QA → Human Gate → Harness Review**，並要求 Spec 分層。