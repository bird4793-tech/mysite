# 國際專案管理與海外營運 | 個人作品集與履歷網站 (Bird Chen Portfolio)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Google Apps Script](https://img.shields.io/badge/Google_Apps_Script-4285F4?style=flat&logo=google&logoColor=white)](https://developers.google.com/apps-script)

> 專為展現國際專案管理、科技與半導體供應鏈營運、跨國公部門計畫統籌經驗設計的高質感單頁式（SPA）個人作品集網站。採用當代雜誌雙欄排版（Magazine Split Layout），具備無伺服器表單串接與響應式互動設計。

---

## 🌟 核心特色 (Key Features)

- **雜誌風格雙欄佈局 (Editorial Split Layout)**：
  - 左側固定個人專業形象、即時導覽錨點與在地資訊。
  - 右側流暢滾動呈現專業經歷、專案成就、格鬥與體能紀律。
- **深色 / 淺色主題自由切換 (Dark/Light Mode Toggle)**：
  - 支援無縫主題切換，搭配細緻的 CSS 變數系統與過渡動畫。
- **無伺服器聯絡表單 (Serverless Contact Form)**：
  - 前端以原生 JavaScript `fetch` 傳輸表單資料。
  - 後端串接 **Google Apps Script (GAS)** Web App，自動將訪客訊息寫入 Google 試算表（Google Sheets），零主機維護成本。
- **背景情境音訊控制 (Ambient Audio Player)**：
  - 內建自訂音訊播放/暫停按鈕與動態狀態圖示，提升瀏覽沉浸感。
- **無依賴輕量架構 (Zero Build Tools)**：
  - 純 HTML5 + 原生 JavaScript + Tailwind CSS CDN + FontAwesome，不需安裝 Node.js 或複雜建置流程，隨開即用。

---

## 🛠️ 技術棧 (Tech Stack)

| 領域 | 使用技術 | 說明 |
| :--- | :--- | :--- |
| **前端結構** | HTML5 / Semantic Elements | 語意化標籤與結構化內容配置 |
| **樣式設計** | Tailwind CSS (CDN) | 現代化實用型 CSS 框架與響應式斷點 |
| **字體排印** | Google Fonts | `Inter` (無襯線正文) + `Playfair Display` (優雅襯線標題) |
| **圖示庫** | Font Awesome 6.4.0 | 輕量向量圖示 |
| **後端資料儲存** | Google Apps Script + Sheets | 無伺服器資料接收端點（RESTful API） |
| **部署相容** | GitHub Pages / Netlify / Vercel | 支援任何靜態網頁託管平台 |

---

## 📂 專案檔案結構 (Project Structure)

```bash
.
├── index.html          # 主要網頁入口文件（包含結構、Tailwind 設定與互動腳本）
├── README.md           # 專案說明文件
└── LICENSE             # 開源授權條款 (選填)
# 複製儲存庫
git clone [https://github.com/](https://github.com/)<your-username>/<your-repo-name>.git

# 進入專案目錄
cd <your-repo-name>

# 透過 Python 啟動輕量伺服器
python3 -m http.server 8000
function doPost(e) {
  try {
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    var data = JSON.parse(e.postData.contents);
    
    // 依序寫入：時間戳記、姓名、Email、訊息內容
    sheet.appendRow([
      new Date(),
      data.name,
      data.email,
      data.message
    ]);
    
    return ContentService
      .createTextOutput(JSON.stringify({ result: 'success' }))
      .setMimeType(ContentService.MimeType.JSON);
  } catch (error) {
    return ContentService
      .createTextOutput(JSON.stringify({ result: 'error', error: error.message }))
      .setMimeType(ContentService.MimeType.JSON);
  }
}
const scriptURL = 'YOUR_NEW_APPS_SCRIPT_WEB_APP_URL';
<ElicitationsGroup message="貼上並儲存後，如果需要進一步檢查或設定：">
  <Elicitation label="排查 Markdown 語法渲染異常" query="我貼上 README 後 GitHub 頁面排版跑掉了，該如何檢查哪裡語法出錯？"/>
  <Elicitation label="檢查試算表是否能正常收信" query="我要如何測試 Google Apps Script 有沒有成功把表單資料寫進 Google 試算表？"/>
  <Elicitation label="建立 LICENSE 開源授權檔案" query="如何在 GitHub 上新增標準的 MIT License 授權檔案？"/>
</ElicitationsGroup>
