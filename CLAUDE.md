# Sep. 久點 官方網站

> 跨層規則(語言、品牌語調、wiki 參考)在 [`../CLAUDE.md`](../CLAUDE.md);本檔只放網站專案專屬規則。

## Stack

| Layer | Technology |
|-------|-----------|
| 前端 | 純 HTML / CSS / JS(單一 index.html,無框架)|
| 部署 | 尚未部署(預計 Zeabur / Cloudflare Pages / Vercel)|
| 網域 | 尚未購買 |

## 檔案結構

| 檔案 | 用途 |
|------|------|
| `index.html` | 整個網站(HTML + CSS + JS 全部在這一個檔案)|
| `images/` | 商品照片、品牌主視覺、LOGO |
| `images/LOGO.jpg` | Favicon 和品牌 logo |
| `images_backup/` | 圖片備份(已 gitignore)|
| `../wiki.md` | 品牌單一事實來源(產品、定價、SOP、品牌定位)|
| `CLAUDE.md` | 本檔,網站專屬工作手冊 |

## 設計規格

| 項目 | 設定 |
|------|------|
| 風格 | 日系極簡,冷米白底色,煙燻綠點綴 |
| 標題字體 | Cormorant Garamond |
| 內文字體 | Noto Serif TC |
| 背景色 | `#F4F2EE` |
| 文字色 | `#1A1A18` |
| 強調色(煙燻綠)| `#3D5E52` |
| 輔助色(焙茶棕)| `#7A6650` |

> 色系與字體鎖定,不可變更。

## 開單機制

每次開單只需修改 `index.html` 最上方的 `<script>` 區塊:

```js
const ORDER_STATUS = "open";  // 開單改 "open"、關單改 "closed"
const ORDER_LINK_PICKUP = "https://forms.gle/面交表單";
const ORDER_LINK_DELIVERY = "https://forms.gle/宅配表單";
```

- 開單:把 `"closed"` 改成 `"open"` → 存檔 → 部署
- 關單:改回 `"closed"` → 存檔 → 部署

## Git 規則

### Commit 規範
- commit message 一律使用繁體中文
- 格式:「[類型] 簡短說明」
  - [新增] 新功能或新區塊
  - [修改] 修改現有功能或樣式
  - [修正] 修 bug
  - [優化] SEO、效能、無障礙
  - [樣式] 純 CSS 調整
  - [文案] 文字內容修改

### 安全規範
- **每次 push 前,必須先確認 `.gitignore` 是否完整**(檢查有沒有新的敏感檔案需要排除)
- push 前一定要先告訴 Kc 有哪些改動,等確認才推
- 嚴禁 force push
- 推送前檢查是否有機密資料(API key、密碼、表單管理連結)
- `.gitignore` 至少要排除:`.env` / `.DS_Store` / `Thumbs.db` / `node_modules` / `*.log`
