請重新建立完整的 CLAUDE.md，內容如下：

# 股票自選清單專案

## 專案說明
個人股票自選清單網頁，支援台股和美股即時報價，結合 Google 帳號登入實現個人化功能。

## 目前技術
- 純 HTML + CSS + JavaScript，單一 index.html 檔案
- Yahoo Finance API 抓取即時股價
- 深色背景介面，上漲紅色，下跌綠色，台股看盤風格

## 頁面架構
- 首頁（未登入）：功能介紹、Google 登入按鈕
- 主頁面（登入後）：個人化股票自選清單、持倉記錄、損益計算

## 開發階段規劃

### 第一階段（已完成）
- 台股和美股自選清單
- Yahoo Finance API 即時股價
- 拖拉排序、新增、刪除股票
- 部署到 GitHub Pages

### 第二階段（進行中）
- Google 帳號登入（OAuth）
- 權限控制：只能讀寫專屬 Google Sheet，不能存取其他 Google 工具
- Google Sheet 當資料庫（持倉記錄、個人預設清單）
- 網頁直接呈現 Google Sheet 資料，不需要進入 Sheet 操作
- 持倉功能：輸入買入賣出價格和數量
- 自動計算未實現損益和已實現損益
- 手機電腦資料同步

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
- 每次修改後提醒我執行 git push 更新 GitHub
- 安全性優先，Google OAuth 只申請最小必要權限

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