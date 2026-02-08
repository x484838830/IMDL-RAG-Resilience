# RAG 韌性評估分析系統 | RAG Resilience Analyzer

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-3.2.0-green.svg)](https://github.com/x484838830/RAG-Resilience-Analyzer)
[![TypeScript](https://img.shields.io/badge/TypeScript-97.5%25-blue.svg)](https://github.com/x484838830/RAG-Resilience-Analyzer)

> 組織韌性問卷自動化分析工具 | Organizational Resilience Survey Analysis Tool
> 
> 專業級組織韌性評估與進階 PDF 報告生成系統

---

## 📥 下載安裝 | Download

### 🇹🇼 中文版（Chinese Version）- 推薦

| 版本 | 下載 | 發布日期 |
|------|------|----------|
| **v3.2.0** | [RAG Resilience Analyzer Chinese Setup 3.2.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v3.2.0-chinese/RAG.Resilience.Analyzer.Chinese.Setup.3.2.0.exe) | 2026-02-08 |
| v3.1.0 | [RAG Resilience Analyzer Chinese Setup 3.1.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v3.1.0-chinese/RAG.Resilience.Analyzer.Chinese.Setup.3.1.0.exe) | 2026-01-28 |

### 🌐 English Version（英文版）

| Version | Download | Release Date |
|---------|----------|--------------|
| **v3.2.0** | [RAG Resilience Analyzer Setup 3.2.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v3.2.0/RAG.Resilience.Analyzer.Setup.3.2.0.exe) | 2026-02-08 |
| v3.0.0 | [RAG Resilience Analyzer Setup 3.0.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v3.0.0/RAG.Resilience.Analyzer.Setup.3.0.0.exe) | 2026-01-20 |

**系統需求 | System Requirements**：Windows 10/11 (64-bit)、4GB RAM、500MB 硬碟空間

---

## ✨ 版本功能 | Version Features

### v3.2.0 新功能 🆕
- 🎨 **圖表外觀自訂**：可選擇 5 種主題色票、調整線條粗細與透明度
- 📊 **Excel 匯出功能**：一鍵匯出分析資料至 Excel 檔案
- 🔀 **表格排序功能**：點擊標題即可排序，快速找出弱項
- 🏢 **組織名稱輸入**：可自訂報告標題，顯示於 PDF 與 Excel 中
- 📁 **自訂顏色支援**：配置檔可新增 `Colors` 工作表自訂各 Potential 顏色

### v3.1.0 中文版功能
- 🌐 **完整中文介面**：所有按鈕、標籤、提示訊息皆為繁體中文
- 📄 **中文 PDF 報告**：匯出的 PDF 報告完整支援中文顯示（嵌入 Noto Sans TC 字體）
- 🔄 **中英文配置檔支援**：Potential 欄位可使用中文或英文

### v3.0.0 核心功能
- 🎨 **重新設計的 PDF 報告**：多頁面專業版面配置
- 📊 **強化的視覺化圖表**：更大的圖表與顏色編碼指標
- 🎯 **三級評分系統**：需要改進 / 中等表現 / 表現良好
- 🛡️ **自動資料品質檢查**：附視覺化警告提示
- 📑 **智慧分頁功能**：可適應任意數量的評估項目

---

## 📋 Potential 名稱對照 | Potential Name Reference

中文版支援以下 Potential 名稱（配置檔可使用中文或英文）：

| 中文 | English | 說明 |
|------|---------|------|
| 回應 | Response | 對例行與突發事件的應對能力 |
| 監控 | Monitor | 持續追蹤關鍵營運指標的能力 |
| 預測 / 預見 | Anticipate | 評估未來威脅與機會的前瞻能力 |
| 學習 | Learn | 從經驗中學習與改善的系統化能力 |

---

## 🔬 評估架構 | Assessment Framework

基於 **Erik Hollnagel** 的韌性工程理論，評估組織的四大核心潛能：

```
        回應 (Response)
              ▲
              │
預見 ◄────────┼────────► 監控
(Anticipate)  │         (Monitor)
              │
              ▼
        學習 (Learn)
```

---

## ✨ 功能特色 | Features

| 功能 | 說明 |
|------|------|
| ✅ 自動化問卷分析 | 上傳 Excel 問卷資料，自動計算分數 |
| ✅ 視覺化報告 | 生成四個 Potential 的雷達圖 |
| ✅ 菱形圖分析 | 顯示各 Potential 面積占比與整體韌性分數 |
| ✅ 匯出 PDF | 一鍵下載完整多頁專業分析報告 |
| ✅ 匯出 Excel | 一鍵匯出分析資料至 Excel 檔案 |
| ✅ 圖表外觀自訂 | 可選擇主題色票、調整線條粗細與透明度 |
| ✅ 表格排序 | 點擊標題即可排序，快速找出弱項 |
| ✅ 完全離線 | 無需網路連線即可使用 |
| ✅ 資料隱私 | 所有資料在本地處理，不上傳雲端 |
| ✅ 三級績效分類 | 更細緻的績效評估（紅/橘/綠） |
| ✅ 資料品質警告 | 自動偵測未定義的回答選項 |

---

## 🛠️ 技術亮點 | Technical Highlights

- 使用 **React 18 + TypeScript + Vite** 打造
- **Tailwind CSS** 響應式設計（桌機 + 行動裝置）
- **Recharts** 圖表庫提供互動式視覺化
- **jsPDF + jspdf-autotable** 專業 PDF 報告生成
- **SheetJS (xlsx)** Excel 檔案匯入匯出
- **Noto Sans TC** 中文字體嵌入（中文版）
- **Electron** 跨平台桌面應用程式框架
- 即時計算與分析，無需伺服器

---

## 📖 使用說明 | User Guide

### 1. 安裝 | Installation

1. 下載對應語言版本的安裝檔
2. 雙擊執行安裝程式
3. 選擇安裝目錄（建議使用預設）
4. 完成安裝

**⚠️ Windows 安全提示：**  
首次執行時可能會出現「Windows 已保護您的電腦」提示，這是正常的。  
點擊「更多資訊」→「仍要執行」即可。

### 2. 準備問卷檔案 | Prepare Files

您需要兩個 Excel 檔案：

#### 📊 問卷資料檔 (Survey Data)
- 包含受訪者填答的 Likert 量表問題
- 格式：每一列是一位受訪者，每一欄是一個問題

#### ⚙️ 配置檔 (Configuration)
需要包含以下工作表：

| 工作表 | 說明 |
|--------|------|
| `Settings` | 問題起始欄位設定 |
| `Likert_Mapping` | 回答選項與分數對應 |
| `Question_Mapping` | 題目與 Potential 對應 |
| `Colors`（選填） | 自訂各 Potential 顏色 |

**💡 提示：** 啟動程式後可點擊「下載配置範本」取得範例檔案。

### 3. 分析流程 | Analysis Process

1. 啟動程式
2. 輸入組織名稱（選填）
3. 上傳「問卷資料檔」和「配置檔」
4. 點擊「開始分析」
5. 調整圖表外觀（主題、線條粗細、透明度）
6. 查看四個雷達圖和菱形圖
7. 點擊「匯出 PDF」或「匯出 Excel」下載報告

---

## 🛠️ 常見問題 | FAQ

### Q: 為什麼無法開啟程式？
**A:** 請確認：
- 您的 Windows 版本是 64 位元
- 已安裝最新的 Windows 更新
- 防毒軟體沒有封鎖程式

### Q: 可以在 Mac 上使用嗎？
**A:** 目前僅支援 Windows，Mac 版本規劃中。

### Q: 資料會被上傳到雲端嗎？
**A:** 不會！所有資料都在您的電腦本地處理，絕不上傳。

### Q: 中文版和英文版有什麼差異？
**A:** 
- 中文版：介面全中文、PDF 報告支援中文、配置檔可用中文 Potential 名稱
- 英文版：介面全英文、PDF 報告英文

### Q: 如何自訂圖表顏色？
**A:** 在配置檔中新增 `Colors` 工作表，格式如下：
| Potential | Color (Hex/Name) |
|-----------|------------------|
| Response | #3b82f6 |
| Monitor | #ef4444 |
| Anticipate | #f97316 |
| Learn | #22c55e |

### Q: 如何卸載？
**A:** 
- 方法 1：執行安裝目錄中的 `Uninstall RAG Resilience Analyzer.exe`
- 方法 2：從 Windows 設定 → 應用程式 → 已安裝的應用程式中卸載

---

## 📝 更新日誌 | Changelog

### v3.2.0 (2026-02-08)
- 🎨 圖表外觀自訂（主題色票、線條粗細、透明度）
- 📊 Excel 匯出功能
- 🔀 表格排序功能
- 🏢 組織名稱輸入
- 📁 配置檔 Colors 工作表支援

### v3.1.0 (2026-01-28) - 中文版
- 🌐 完整中文介面
- 📄 中文 PDF 報告（嵌入 Noto Sans TC 字體）
- 🔄 支援中英文配置檔

### v3.0.0 (2026-01-20)
- 🎨 重新設計的多頁 PDF 報告
- 🎯 三級績效分類系統
- 🛡️ 資料品質警告強化

### v2.0.0 (2026-01-15)
- 🖥️ Windows 桌面應用程式
- ⚠️ 資料警告系統

### v1.0.0 (2026-01-02)
- 🎉 首次發布

完整更新日誌請參閱 [CHANGELOG.md](./CHANGELOG.md)

---

## 👥 作者 | Author

**Lo, Hsuan-Hao（羅軒澔）**
- GitHub: [@x484838830](https://github.com/x484838830)
- Email: x484838830@gmail.com

**Chuang, Sheuwen（莊秀文）**
- Email: sheuwen@tmu.edu.tw
---

## 🙏 致謝 | Acknowledgments

感謝所有提供回饋與建議的貢獻者和使用者！

特別感謝：
- [Erik Hollnagel](https://erikhollnagel.com/) - 韌性工程 RAG 理論創始人
- 台北醫學大學數據科學研究所 莊秀文教授

---

## 📧 聯絡方式 | Contact

- **問題回報**：[GitHub Issues](https://github.com/x484838830/RAG-Resilience-Analyzer/issues)
- **功能建議**：[GitHub Discussions](https://github.com/x484838830/RAG-Resilience-Analyzer/discussions)
- **電子郵件**：x484838830@gmail.com

---

## 📄 授權 | License

本軟體僅供學術研究使用。| For academic research use only.

---

**⭐ 如果這個專案對您有幫助，請給我們一個 Star！**

**⭐ If this project helps you, please give us a Star!**

Made with ❤️ by [Hsuan-Hao Lo](https://github.com/x484838830)
