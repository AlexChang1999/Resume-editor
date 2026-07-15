# Resume Editor 專案規則

## 雙語（i18n）規則

本專案介面支援中/英雙語切換（`#langToggle` + `i18n.zh` / `i18n.en` 物件）。

**新增任何使用者可見文字（按鈕、label、placeholder、提示文字）時，務必同步新增英文翻譯：**

1. 在 `i18n.zh` 與 `i18n.en` 物件各加一組對應 key。
2. 若是靜態文字（label/button），該元素要有唯一 `id`，並在 `updateLanguage()` 函式裡加一行 `document.getElementById('xxx').innerText = lang.xxx;`。
3. 若是 `placeholder`，同樣在 `updateLanguage()` 裡設定 `document.getElementById('xxx').placeholder = lang.xxx;`。
4. 改完後務必手動切換 `#langToggle` 兩個方向各測一次，確認沒有殘留中文、沒有 console 錯誤。

**常見疏漏**：只加中文寫死在 HTML 裡（例如 `<button>新增</button>`），忘記掛 `id` 和 `i18n` 對應，導致切到英文介面時該文字沒有跟著變。過去發生過（新增技能、新增經歷、新增教育、下載PDF按鈕漏翻），修正時列入 i18n 檢查清單。
