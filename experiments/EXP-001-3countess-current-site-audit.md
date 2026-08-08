---
id: EXP-001-3countess-current-site-audit
experiment: EXP-001-donix-product-delivery-harness
status: draft
created_at: 2026-08-08
source: public_site_review
---

# EXP-001｜3countess Current Site Audit

## Audit scope
只記錄 2026-08-08 對公開網站的可觀察現況。此檔不等於 Owner Truth，也不代表所有問題都已驗證為商業原因。

## 已知事實｜Public site

- 網站主導覽同時包含：生活選物、複方精油、精選茶品、優惠組合、預購商品、關於三爵。
- 首頁目前「最新上架」主要呈現襪子類生活選物。
- 關於頁品牌表述包含「嚴選質感生活」與「時尚輕鬆入手」，已超出單純茶品牌敘事。
- 網站 title / copyright 仍以「三爵茶葉」為主要名稱表達。
- 精選茶品分類目前有多個茶葉、茶包與優惠組合。
- 生活選物分類目前主要由女襪、中性襪、運動／機能／瑜伽襪、潮流襪構成。
- 首頁公開內容仍可讀到多組模板 placeholder，例如 `A smaller header`、`Add Some Corporate Header Here`、Lorem ipsum。
- 商品分類頁仍可讀到 WooCommerce sidebar widget placeholder：`You need to assign Widgets to Shop Sidebar...`。

## Audit findings｜donix interpretation

### A1｜Brand Architecture mismatch
Client Truth 已確認三爵是「質感生活選物品牌」，但現站仍同時保留「三爵茶葉」主識別、茶品牌歷史與大量跨類別商品。這會使新客難以快速理解「三爵到底是什麼」。

### A2｜Merchandising hierarchy unclear
首頁新品大量由襪子主導，但 Owner 已定義茶與生活選物同為主力，且目前真正成交證據只有茶。現站沒有明確說明「茶」與「生活選物」在 Master Brand 下的角色與優先層級。

### A3｜Navigation mirrors catalog, not decision journey
現導覽主要以商品類別直接展開，對「第一次認識三爵」「想買茶」「想找生活好物」「想送禮」等不同任務缺乏清楚分流。

### A4｜Trust/content debt
公開頁面仍有模板 placeholder 與後台元件提示殘留，會降低完成度與品牌信任感；需要在新站 migration 前完整盤點。

### A5｜Evidence gap for lifestyle selection
生活選物被 Owner 定義為主力，但目前尚未有成交證據，因此不應直接把生活選物的 IA、首頁曝光或投資幅度寫成既定答案。應以可低成本驗證的方式進入網站架構與後續投放。

## 尚未驗證

- 現站實際轉換率與流量。
- 哪一頁造成最大流失。
- 茶 vs 生活選物在廣告上的 CAC / CVR。
- 現站會員、SEO、網址資產的實際價值。
- 各商品頁內容與法規風險是否全面一致。
- 現站 placeholder 是否在所有前端情境都可見。

## Audit Priority

P0：Brand Architecture / 商品層級 / 主要購買入口。
P1：首頁與導航的 decision journey、PDP trust content、廣告承接。
P1：舊站內容與 SEO migration 清單。
P2：會員、進階推薦、內容擴張與其他非核心功能。
