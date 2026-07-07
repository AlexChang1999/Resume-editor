# 📄 Resume Editor — 動態履歷產生器

<p align="center">
  <b>即時預覽・一鍵匯出 PDF・零依賴、零後端，單一 HTML 檔搞定</b>
</p>

<p align="center">
  <a href="https://alexchang1999.github.io/Resume-editor/"><img src="https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-2ea44f?logo=github" alt="Live Demo"></a>
  <img src="https://img.shields.io/badge/Vanilla%20JS-No%20Framework-f7df1e?logo=javascript&logoColor=black" alt="Vanilla JS">
  <img src="https://img.shields.io/badge/Dependencies-0-blue" alt="Zero Dependencies">
  <img src="https://img.shields.io/badge/i18n-%E4%B8%AD%E6%96%87%20%2F%20English-orange" alt="i18n">
</p>

---

## ✨ 這是什麼？

一個**開箱即用的線上履歷編輯器**：左邊填資料，右邊即時渲染出 A4 排版的履歷，滿意了直接按一鍵存成 PDF。全部功能都在**一個 `index.html`** 裡完成——沒有框架、沒有建置流程、沒有伺服器，打開瀏覽器就能用。

👉 **[立即體驗 Live Demo](https://alexchang1999.github.io/Resume-editor/)**

## 🚀 功能特色

| 功能 | 說明 |
|------|------|
| ⚡ **即時預覽** | 每個輸入框都即時同步到右側 A4 畫布，所見即所得 |
| 🖨️ **一鍵匯出 PDF** | 透過瀏覽器列印功能輸出，`@media print` 已優化分頁與色彩 |
| 💾 **自動儲存** | 輸入停止 500ms 後自動寫入 `localStorage`（debounce），重新整理不掉資料 |
| 📦 **JSON 備份 / 還原** | 一鍵匯出完整履歷資料為 JSON，換裝置、換瀏覽器都能無痛搬家 |
| 🌐 **中英雙語介面** | 一個開關切換全站繁中 / English，欄位標籤與預覽區同步翻譯 |
| 📷 **大頭照上傳** | 圖片以 base64 內嵌儲存，含 2MB 大小防護與空間不足降級處理 |
| 🎨 **自訂主題色** | 色票選擇器直接改 CSS 變數，即時套用整份履歷配色 |
| 🧩 **動態欄位** | 工作經歷、教育背景、技能標籤皆可自由新增 / 刪除 |
| 🙈 **隱私開關** | 大頭照、期待薪資、作品集連結可個別隱藏，一份履歷多種投法 |

## 🏁 快速開始

不需要安裝任何東西：

```bash
git clone https://github.com/AlexChang1999/Resume-editor.git
cd Resume-editor
# 直接用瀏覽器打開 index.html 即可
```

或者——直接使用 [GitHub Pages 線上版](https://alexchang1999.github.io/Resume-editor/)。

## 🛠️ 技術棧

- **HTML5 + CSS3**：Flexbox 版面、CSS Variables 主題系統、`@media print` 列印優化
- **Vanilla JavaScript**：無任何框架與第三方套件
- **Web APIs**：`localStorage`（自動儲存）、`FileReader`（照片與 JSON 匯入）、`Blob` + Object URL（JSON 匯出）
- **部署**：GitHub Pages 靜態託管

## 🧠 設計重點

**為什麼堅持單檔、零依賴？** 履歷編輯器的核心價值是「隨時打得開」——單一 HTML 檔案讓它可以離線使用、直接寄給別人、丟到任何靜態空間就能跑，不會因為套件過期而壞掉。

其他值得一提的實作細節：

- **事件委派（Event Delegation）**：自動儲存只在編輯面板掛一組 `input` / `change` listener，之後動態新增的欄位自然被涵蓋，不需逐一綁定。
- **防禦式儲存**：照片超過 2MB 或 `localStorage` 空間不足（`QuotaExceededError`）時，自動退回「不存照片」模式並提醒使用者改用 JSON 備份；隱私模式下 `localStorage` 完全不可用也不影響編輯。
- **資料版本化**：儲存格式帶有 `version` 欄位，未來 schema 變更時可以做遷移判斷；損毀資料一律清除並回退預設值，頁面永不白屏。
- **匯出補位**：JSON 匯出沒有 5MB 限制，永遠包含照片——正是 `localStorage` 存不下照片時的備援方案。

## 🔒 資料與隱私

所有資料**只存在你自己的瀏覽器**（`localStorage`）裡，不會上傳到任何伺服器。注意：`localStorage` 依網域隔離，本機 `file://` 開啟與 GitHub Pages 線上版的資料互不相通，跨環境請使用 JSON 匯出 / 匯入。

## 📄 免責聲明

本專案僅供展示開發能力使用，頁面中的範例資料皆為虛構，敏感資訊已做去識別化處理。
