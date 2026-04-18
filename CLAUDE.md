# 股票自選清單專案

## 專案說明
個人股票自選清單網頁，支援台股和美股即時報價，結合 Google 帳號登入實現個人化功能。供個人及親友使用。

## 目前技術
- 純 HTML + CSS + JavaScript，單一 index.html 檔案
- Yahoo Finance API 抓取即時股價
- Google Identity Services (GIS) 處理 OAuth 登入
- Google Sheets API 當資料庫
- 部署在 GitHub Pages

## 預設股票清單
- 台股：台積電(2330)、聯發科(2454)、台達電(2308)
- 美股：TSM.US、NVDA、GOOG

## 頁面架構
- 首頁（未登入）：功能介紹、Google 登入按鈕
- 主頁面（登入後）：個人化股票自選清單、持倉記錄、損益計算

## Google Sheet 資料庫
- Sheet 名稱：stock-watchlist-db
- 登入後自動在使用者的 Google Drive 建立此 Sheet
- 自動建立三個工作表並加入中文標題列：
  - watchlist：市場、代號、名稱、排序
  - portfolio：代號、名稱、持股數量、平均成本、市場
  - transactions：日期、代號、名稱、買賣、價格、股數
- Sheet 空白時自動寫入預設股票清單，不顯示任何錯誤

## 功能規劃

### 第一階段（已完成）
- 台股和美股自選清單
- Yahoo Finance API 即時股價
- 拖拉排序、新增、刪除股票
- 部署到 GitHub Pages

### 第二階段（進行中）
- Google 帳號登入（OAuth）
- 權限控制：只能讀寫專屬 Google Sheet，不能存取其他 Google 工具
- 登入後自動建立並初始化使用者的 stock-watchlist-db
- 網頁直接呈現 Google Sheet 資料，不需要進入 Sheet 操作
- 手機電腦資料同步
- 持倉記錄功能：
  - 可輸入日期、股票代號、買入/賣出、價格、股數
  - 自動計算平均成本
  - 未實現損益（使用即時股價計算）
  - 已實現損益統計
  - 歷史買賣記錄列表
  - 所有資料存入 portfolio 和 transactions 工作表

### 第三階段（計畫中）
- MCP 整合
- 連接瀏覽器自動抓財經新聞顯示在自選股旁邊
- 自動把每天股價記錄到 Google Sheet

### 第四階段（計畫中）
- Agent 自動化
- 每日早報 Agent：每天早上自動抓股價和新聞，用 AI 分析後發送到 LINE 或 Email
- 價格警報 Agent：監控股價超過設定價格自動通知
- 新聞摘要 Agent：自動搜尋自選股相關新聞並整理重點

## 開發規則
- 請用繁體中文回覆
- 修改程式前先說明要做什麼再動手
- 每次修改後說明改了什麼
- 保持程式碼在單一 index.html 檔案
- 每次修改後提醒執行 git push 更新 GitHub
- 安全性優先，Google OAuth 只申請最小必要權限
- 介面永遠依照下方介面規範

## 介面規範
- 整體風格：Apple 淺灰科技感
- 整體背景：#F5F5F7
- 頁首背景：#FFFFFF，底部加 1px 細線 #D2D2D7
- 股票卡片：白色背景 #FFFFFF，無陰影，無邊框
- 台股區塊底色：#F0F4FF（淡藍灰）
- 美股區塊底色：#F0F7F0（淡綠灰）
- 股票名稱：#1D1D1F，16px
- 股票代號：#6E6E73，12px
- 股價：22px
- 漲跌幅：14px
- 上漲：#FF3B30
- 下跌：#34C759
- 無變化：#6E6E73
- 按鈕：#0071E3
- 字型：-apple-system, BlinkMacSystemFont, "SF Pro Display", sans-serif

## OAuth 設定
- Client ID 和 Sheet ID 請勿寫在此檔案
- Token 存在 sessionStorage（關閉瀏覽器自動登出）