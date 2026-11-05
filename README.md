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
  - 前端以原生 JavaScript fetch 傳輸表單資料。
  - 後端串接 Google Apps Script (GAS) Web App，自動將訪客訊息寫入 Google 試算表（Google Sheets），零主機維護成本。
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
| **字體排印** | Google Fonts | Inter (無襯線正文) + Playfair Display (優雅襯線標題) |
| **圖示庫** | Font Awesome 6.4.0 | 輕量向量圖示 |
| **後端資料儲存** | Google Apps Script + Sheets | 無伺服器資料接收端點（RESTful API） |
| **部署相容** | GitHub Pages / Netlify / Vercel | 支援任何靜態網頁託管平台 |

---

## 📂 專案檔案結構 (Project Structure)

- `index.html`：主要網頁入口文件（包含結構、Tailwind 設定與互動腳本）
- `README.md`：專案說明文件
- `LICENSE`：開源授權條款 (選填)

---

## 🚀 快速上手 (Quick Start)

### 本地預覽 (Local Preview)

本專案為純靜態架構，可直接使用任何靜態伺服器開啟：

1. 複製儲存庫：`git clone https://github.com/<your-username>/<your-repo-name>.git`
2. 進入專案目錄：`cd <your-repo-name>`
3. 透過 Python 啟動輕量伺服器：`python3 -m http.server 8000`
4. 瀏覽器開啟 `http://localhost:8000` 即可預覽。

---

## ⚙️ 後端設定教學：Google Apps Script 聯絡表單

本專案的聯絡表單透過 Google Apps Script 將訪客訊息儲存至 Google 試算表。若要使用自己的試算表接收訊息，請依照以下步驟設定：

### 步驟 1：建立 Google 試算表
1. 前往 Google Sheets 新增一份空白試算表。
2. 將第一列欄位分別命名為：Timestamp、Name、Email、Message。

### 步驟 2：建立 Apps Script 專案
1. 點擊頂部選單的 **擴充功能 (Extensions)** > **Apps Script**。
2. 將編輯器內的程式碼替換為處理 POST 請求並寫入試算表的腳本。

### 步驟 3：部署為 Web 應用程式 (Web App)
1. 點擊右上角的 **部署 (Deploy)** > **新增部署作業 (New deployment)**。
2. 類型選擇 **網頁應用程式 (Web app)**。
3. 設定：
   - 說明 (Description)：Contact Form Webhook
   - 執行身分 (Execute as)：我 (Me)
   - 誰可以存取 (Who has access)：所有人 (Anyone)（*務必設為所有人，表單才能在免登入狀態下送出*）
4. 點擊 **部署**，複製產生的 **網頁應用程式網址 (Web App URL)**。

### 步驟 4：替換前端 API 網址
打開 `index.html`，搜尋 `handleFormSubmit` 函式，將 `scriptURL` 替換為你的 Web App URL。

---

## 🌐 部署至 GitHub Pages

1. 前往 GitHub 儲存庫的 **Settings** > **Pages**。
2. 在 **Branch** 選取 `main` 分支與 `/ (root)` 資料夾後點擊 **Save**。
3. 稍候片刻即可透過 `https://<your-username>.github.io/<your-repo-name>/` 瀏覽上線網站。

---

## 📄 授權條款 (License)

本專案依據 [MIT 授權條款](LICENSE) 進行開源。
