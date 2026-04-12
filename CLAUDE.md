# Sep. 久點 官方網站

## 專案簡介

Sep. 久點（Sep. Dessert Studio）的品牌官網。
以抹茶為核心的手作甜點工作室，位於新北，透過 Instagram 不定期開單。

## Stack

| Layer | Technology |
|-------|-----------|
| 前端 | 純 HTML / CSS / JS（單一 index.html，無框架）|
| 部署 | 尚未部署（預計使用 Zeabur / Cloudflare Pages / Vercel）|
| 網域 | 尚未購買 |

## 檔案結構

| 檔案 | 用途 |
|------|------|
| `index.html` | 整個網站（HTML + CSS + JS 全部在這一個檔案）|
| `images/` | 商品照片、品牌主視覺、LOGO |
| `images/LOGO.jpg` | Favicon 和品牌 logo |
| `sep-dessert-wiki.md` | 品牌知識庫（產品、定價、SOP、品牌定位）— 單一事實來源 |
| `CLAUDE.md` | 本檔案，Claude Code 的工作手冊 |

## 設計規格

| 項目 | 設定 |
|------|------|
| 風格 | 日系極簡，冷米白底色，煙燻綠點綴 |
| 標題字體 | Cormorant Garamond |
| 內文字體 | Noto Serif TC |
| 背景色 | `#F4F2EE` |
| 文字色 | `#1A1A18` |
| 強調色（煙燻綠）| `#3D5E52` |
| 輔助色（焙茶棕）| `#7A6650` |

## 開單機制

每次開單只需修改 `index.html` 最上方的 `<script>` 區塊：

```js
const ORDER_STATUS = "open";  // 開單改 "open"、關單改 "closed"
const ORDER_LINK_PICKUP = "https://forms.gle/面交表單";
const ORDER_LINK_DELIVERY = "https://forms.gle/宅配表單";
```

- 開單：把 `"closed"` 改成 `"open"` → 存檔 → 部署
- 關單：改回 `"closed"` → 存檔 → 部署

## Git 規則

### Commit 規範
- commit message 一律使用繁體中文
- 格式：「[類型] 簡短說明」
  - [新增] 新功能或新區塊
  - [修改] 修改現有功能或樣式
  - [修正] 修 bug
  - [優化] SEO、效能、無障礙
  - [樣式] 純 CSS 調整
  - [文案] 文字內容修改

### 安全規範
- **每次 push 前，必須先確認 .gitignore 是否完整**（檢查有沒有新的敏感檔案需要排除）
- push 前一定要先告訴我有哪些改動，等我確認才推
- 嚴禁 force push
- 推送前檢查是否有機密資料（API key、密碼、表單管理連結）
- .gitignore 要排除：.env / .DS_Store / Thumbs.db / node_modules / *.log

### 對我的說明
- 我不熟悉 git，每次執行 git 操作時請用白話解釋
- 不要用 git 術語，用「存檔」「上傳」「版本紀錄」之類的說法

## 品牌語調

撰寫文案、社群內容或網站文字時：
- 溫暖、有個性、不制式
- 像一個真實的人在說話，不像品牌發稿
- 可以有點個人感，但不過度
- 主廚名稱是 Kc

## 溝通語言

- 一律使用繁體中文台灣用語
- 嚴禁使用簡體字或中國大陸用語

## 重要參考

- `sep-dessert-wiki.md` 是品牌的單一事實來源（產品、定價、SOP、品牌定位）
- 任何決策如果改變了 wiki 中的事實，要主動提醒我更新 wiki
- 定價規則、產能限制、成本模型等細節都在 wiki 裡，不要在這裡重複
