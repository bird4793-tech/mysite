Bird Chen - Personal Portfolio & Resume Website國際專案管理與海外營運 | 個人作品集與履歷網站專為展現半導體海外營運、跨國專案管理（包含政府補助案與國際大型科技展統籌）設計的單頁式（SPA）個人品牌與履歷網頁。採用現代雜誌感雙欄排版（Magazine Split Layout），具備無伺服器聯絡表單、深淺色切換與沉浸式情境音訊功能。🌟 核心特色 (Features)雜誌風格雙欄佈局 (Magazine Split Layout)左側固定個人頭像、職銜標註、即時跳轉錨點與版權資訊。右側流暢滾動閱讀個人簡歷、核心專長領域、工作時間軸與個人自律鍛鍊（泰拳與菲律賓武術）。深色 / 淺色模式切換 (Dark / Light Mode)支援一鍵切換日夜間主題，並具備優雅的過渡色彩與 Toast 狀態提示。無伺服器聯絡表單 (Serverless Contact Form)前端使用原生 JavaScript 非同步 fetch 傳送資料。後端串接 Google Apps Script (GAS) Webhook，將訪客訊息直接自動寫入 Google 試算表（Google Sheets），完全免架設伺服器。情境背景音樂播放 (Ambient Audio Player)內建自訂控制開關與動畫脈衝提示，提升網頁互動體驗。極致輕量、隨開即用 (Zero-Build Setup)純 HTML5 + 原生 JavaScript + Tailwind CSS CDN + FontAwesome，不需安裝 Node.js 或複雜建置工具。🛠️ 技術架構 (Tech Stack)領域技術 / 服務說明前端結構HTML5 / Semantic Elements語意化結構與無障礙標籤設計樣式框架Tailwind CSS (CDN)響應式斷點與排版設計字體排印Google FontsInter（內文無襯線體） + Playfair Display（大標襯線體）圖示庫Font Awesome 6.4.0輕量向量圖示後端儲存Google Apps Script + Google Sheets無伺服器資料庫與表單接收端點佈署支援GitHub Pages / Netlify / Vercel純靜態代管相容📂 專案結構 (Directory Structure).
├── index.html       # 網站主檔案（包含 HTML、Tailwind 設定與所有互動 JS）
├── README.md        # 儲存庫專案說明文件
└── LICENSE          # 開源授權條款 (MIT)
🚀 本地執行 (Local Development)由於本專案為零建置靜態頁面，你可以直接以瀏覽器開啟 index.html，或使用任何輕量本機伺服器：# 1. 複製儲存庫
git clone https://github.com/<your-username>/<your-repo-name>.git

# 2. 進入目錄
cd <your-repo-name>

# 3. 使用 Python 啟動本地伺服器
python3 -m http.server 8000
接著在瀏覽器打開 http://localhost:8000 即可預覽。⚙️ 後端串接教學：Google Apps Script 表單接收網頁中的聯絡表單預設透過 Google Apps Script 寫入 Google 試算表。若需要設定為自己的試算表接收，請按以下步驟操作：1. 建立 Google 試算表開啟 Google Sheets 建立一份空白試算表。在第 1 列依序填入標題：A1: 時間戳記 (Timestamp)B1: 姓名 (Name)C1: 電子郵件 (Email)D1: 訊息內容 (Message)2. 編寫 Apps Script點擊頂部選單 擴充功能 (Extensions) > Apps Script。將編輯器內所有預設內容刪除，貼上以下程式碼：function doPost(e) {
  try {
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    var data = JSON.parse(e.postData.contents);
    
    // 將資料依序新增至最新一列
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
3. 部署為網頁應用程式 (Web App)點擊右上角 部署 (Deploy) > 新增部署作業 (New deployment)。齒輪圖示選擇 網頁應用程式 (Web app)。參數設定：說明 (Description)：Contact Form Webhook執行身分 (Execute as)：我 (Me)誰可以存取 (Who has access)：所有人 (Anyone) (注意：若未設為 Anyone，未登入的訪客將無法送出表單)點擊 部署，並複製產生的 網頁應用程式網址 (Web App URL)。4. 更新前端端點網址開啟 index.html，找到 handleFormSubmit 函式中的 scriptURL 變數並替換：const scriptURL = 'YOUR_APPS_SCRIPT_WEB_APP_URL';
🌐 一鍵啟用 GitHub Pages將本專案推送到你的 GitHub Public Repo。進入儲存庫頁面，點擊 Settings > 側邊欄 Pages。在 Build and deployment 下方的 Source 選擇 Deploy from a branch。Branch 選擇 main（或 master），資料夾選擇 / (root)，點擊 Save。稍等 1~2 分鐘，即可透過 https://<your-username>.github.io/<your-repo-name>/ 瀏覽線上網站！📄 授權條款 (License)本專案採用 MIT License 授權開放。
