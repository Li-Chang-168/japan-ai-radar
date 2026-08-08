# EXP-000 Scorecard｜Harness Replay Test

使用方式：完成 Replay 後，由 Human 依 Ground Truth 評分。不要讓產出 Agent 自評。

## 評分

每項 0–2 分，滿分 16 分。

| 維度 | 0 分 | 1 分 | 2 分 | Score |
|---|---|---|---|---:|
| Ground Truth alignment | 多個核心結論錯誤 | 大致正確但需修正 | 核心決策高度一致 | |
| Business judgment | 偏功能 / 表面需求 | 有商業考量但優先級弱 | 能抓到真正問題與優先級 | |
| Brand alignment | 明顯偏離品牌 | 基本符合但有通用模板感 | 能維持品牌差異與禁區 | |
| Conversion / UX logic | 動線不完整 / 無轉換邏輯 | 可用但一般化 | 清楚支援搜尋、理解、信任、轉換 | |
| Completeness without bloat | 缺漏或大量無效內容 | 尚可 | 足夠完整且沒有為完整而完整 | |
| Need for re-explanation | ≥ 6 次 | 4–5 次 | ≤ 3 次 | |
| Reusable knowledge | 0–1 個 | 2 個 | ≥ 3 個 | |
| Process overhead | 比直接 Prompt 明顯更重 | 成本與收益接近 | 明顯降低後續重複工作 | |

## Critical Errors

以下不以總分抵銷；任何一項都要單獨記錄：

- [ ] 錯誤理解品牌定位
- [ ] 錯誤理解主要商業目標
- [ ] 提出已明確禁止的策略
- [ ] 轉換路徑與客群需求不一致
- [ ] 自行改變已知技術 / 平台邊界
- [ ] 將尚未驗證假設寫成既定事實

Critical errors count: ____

## Time Log

- Ground Truth：____ min
- Context Pack：____ min
- Consult Replay：____ min
- Spec Replay：____ min
- Compare：____ min
- Harness Review：____ min
- **Total：____ min**

## Re-explanation Log

每當 Human 必須重新解釋一次既有判斷，就記一筆：

1. 
2. 
3. 
4. 
5. 

Total: ____

## Candidate Reusable Assets

只記錄跨專案可能重用的內容：

1. Rule / Checklist：
   - 為什麼可跨專案：
2. Rule / Checklist：
   - 為什麼可跨專案：
3. Rule / Checklist：
   - 為什麼可跨專案：

## Final Decision

- [ ] ADOPT → 進 EXP-001
- [ ] ITERATE → EXP-000B，只簡化、不加架構
- [ ] REJECT → 回到高品質 Prompt workflow

### Decision rationale


### 最重要的新發現


### 下一次絕對不要再增加的複雜度

