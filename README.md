# RAG 韌性評估分析系統

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-3.0.0-green.svg)](https://github.com/x484838830/RAG-Resilience-Analyzer)
[![TypeScript](https://img.shields.io/badge/TypeScript-97.5%25-blue.svg)](https://github.com/x484838830/RAG-Resilience-Analyzer)

> 組織韌性問卷自動化分析工具
> 版本 3.0.0 - 專業級組織韌性評估與進階 PDF 報告生成系統

## 📥 下載安裝

### Windows 10/11 (64位元)

👉 **[點此下載最新版本](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/latest)**

**目前版本：** v3.0.0  
**檔案大小：** 約 200 MB  
**更新日期：** 2025-01-20

---

## ✨ 3.0.0 版本新功能

### 🎨 重新設計的 PDF 報告
我們的 PDF 匯出功能已從頭重新打造，提供企業級的專業報告：

- **多頁面專業版面配置**，每個韌性潛能均有專屬分析頁面
- **強化的視覺化圖表**，包含更大的圖表與顏色編碼指標
- **三級評分系統**（需要改進 / 中等表現 / 表現良好），提供更細緻的績效評估
- **自動資料品質檢查**，附視覺化警告提示
- **智慧分頁功能**，可適應任意數量的評估項目

---

### 評估架構
- 基於 **Erik Hollnagel** 的韌性工程理論
- 評估四大核心潛能：
  - **回應（Response）**：對例行與突發事件的應對能力
  - **監控（Monitor）**：持續追蹤關鍵營運指標的能力
  - **預見（Anticipate）**：評估未來威脅與機會的前瞻能力
  - **學習（Learn）**：從經驗中學習與改善的系統化能力

---

## ✨ 功能特色

- ✅ **自動化問卷分析**：上傳 Excel 問卷資料，自動計算分數
- ✅ **視覺化報告**：生成四個 Potential 的雷達圖
- ✅ **菱形圖分析**：顯示各 Potential 面積占比
- ✅ **匯出 PDF**：一鍵下載完整分析報告
- ✅ **完全離線**：無需網路連線即可使用
- ✅ **資料隱私**：所有資料在本地處理，不上傳雲端

---

### 技術亮點
- 使用 React 18 + TypeScript + Vite 打造
- Tailwind CSS 響應式設計（桌機 + 行動裝置）
- Recharts 圖表庫提供互動式視覺化
- 即時計算與分析
- 專業 PDF 報告匯出
- 無需伺服器 - 完全在瀏覽器中執行（隱私保護）

---

## 🖥️ 系統需求

- **作業系統**：Windows 10/11 (64位元)
- **記憶體**：建議 4GB 以上
- **硬碟空間**：500MB 可用空間
- **網路**：僅安裝時需要（使用時可離線）

---

## 📖 使用說明

### 1. 安裝

1. 下載 `RAG Resilience Analyzer Setup 1.0.0.exe`
2. 雙擊執行安裝程式
3. 選擇安裝目錄（建議使用預設）
4. 完成安裝

**⚠️ Windows 安全提示：**  
首次執行時可能會出現「Windows 已保護您的電腦」提示，這是正常的。  
點擊「更多資訊」→「仍要執行」即可。

### 2. 準備問卷檔案

您需要兩個 Excel 檔案：

#### 📊 問卷資料檔 (Survey Data)
- 包含受訪者填答的 Likert 量表問題
- 格式：每一列是一位受訪者，每一欄是一個問題

#### ⚙️ 配置檔 (Configuration)
- 定義問題對應的 Potential 和 Focus
- 定義 Likert 量表的分數對應

**💡 提示：** 啟動程式後可點擊「下載配置範本」取得範例檔案。

### 3. 分析流程

1. 啟動 `RAG Resilience Analyzer`
2. 上傳「問卷資料檔」和「配置檔」
3. 點擊「開始分析」
4. 查看四個雷達圖和菱形圖
5. 點擊「匯出 PDF」下載報告

---

## 🛠️ 常見問題

### Q: 為什麼無法開啟程式？
**A:** 請確認：
- 您的 Windows 版本是 64 位元
- 已安裝最新的 Windows 更新
- 防毒軟體沒有封鎖程式

### Q: 可以在 Mac 上使用嗎？
**A:** 目前僅支援 Windows，Mac 版本規劃中。

### Q: 資料會被上傳到雲端嗎？
**A:** 不會！所有資料都在您的電腦本地處理，絕不上傳。

### Q: 如何卸載？
**A:** 
- 方法 1：執行安裝目錄中的 `Uninstall RAG Resilience Analyzer.exe`
- 方法 2：從 Windows 設定 → 應用程式 → 已安裝的應用程式中卸載

---

## 📝 更新日誌

### v3.0.0 (2025-01-20)
- ✅ 重新設計的 PDF 報告
- ✅ 版面優化增強使用這體驗


### v1.0.0 (2025-01-02)
- 🎉 首次發布
- ✅ 支援四個 Potential 分析
- ✅ 雷達圖與菱形圖視覺化
- ✅ PDF 報告匯出

---

## 📧 聯絡我們

- **問題回報**：[GitHub Issues](https://github.com/x484838830/RAG-Resilience-Analyzer/issues)
- **功能建議**：歡迎在 Issues 中提出

---

## 📄 授權

本軟體僅供學術研究使用。

---

## 👥 作者

**Lo, Hsuan-Hao**
- GitHub: [@x484838830](https://github.com/x484838830)
- Email: x484838830@gmail.com

## 🙏 致謝

感謝所有提供回饋與建議的貢獻者和使用者！

特別感謝：
- [Erik Hollnagel](https://erikhollnagel.com/) - 韌性工程RAG理論創始人
- 台北醫學大學數據科學研究所
- 國家科學及技術委員會

## 📞 聯絡方式

- 問題回報：[GitHub Issues](https://github.com/x484838830/RAG-Resilience-Analyzer/issues)
- 功能建議：[GitHub Discussions](https://github.com/x484838830/RAG-Resilience-Analyzer/discussions)
- 電子郵件：x484838830@gmail.com


---

**⭐ 如果這個專案對您有幫助，請給我們一個 Star！**

Made with ❤️ by [Hsuan-Hao Lo](https://github.com/x484838830)
