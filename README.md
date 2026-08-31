# IMDL RAG PRO — RAG 韌性評估分析系統 | RAG Resilience Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-5.6.0-green.svg)](https://github.com/x484838830/RAG-Resilience-Analyzer)
[![TypeScript](https://img.shields.io/badge/TypeScript-97.5%25-blue.svg)](https://github.com/x484838830/RAG-Resilience-Analyzer)

> 組織韌性評估平台 | Organizational Resilience (RAG) Assessment Platform
> 
> 問卷設計、批次發送、RAG 分析、AI 報告、韌性能力比較與醫院韌性指數（HRI）；提供網頁版與 Windows 桌面版

---

## 📥 下載安裝 | Download

### 🌐 最新版本 | Latest Version

| 版本 | 下載 | 發布日期 |
|------|------|----------|
| **v5.6.0** | [IMDL RAG PRO Setup 5.6.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v5.6.0/IMDL.RAG.PRO.Setup.5.6.0.exe) | 2026-08-31 |
| **Analyzer** | [IMDL_RAG_Analyzer.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/IMDL_RAG_Analyzer/RAG.Analyzer.Setup.exe) | 2026-05-04 |

**系統需求 | System Requirements**：Windows 10/11 (64-bit)、4GB RAM、1000MB 硬碟空間

---

## ✨ 版本功能 | Version Features

### v5.6.0 新功能 🆕
- 🧭 **資料總覽兩步驟引導**：「第一步 · 選擇比較方式」兩張大卡（趨勢分析／跨部門比較）＋第二步動態指示整行橫幅，第一次使用也知道要點哪裡；一次只開放一種選取方向，選過的模式各機記憶
- 📈 **多部門趨勢分析**：趨勢模式可勾選多個部門一起看跨期變化——每部門一卡總覽、一部門一線的趨勢折線圖（潛能切換、只連各部門實際測量點）、部門 × 期別分數明細；無需指定初始分數
- 🎨 **跨期比較雷達圖升級**：完整歷程一律全畫、圖例點選顯示／隱藏各期、滑過高亮、色點展開七色調色盤自選線色（各機各計畫記憶）；取消超過 5 筆默默剪枝
- 🏷️ **術語統一**：「初始分數／中間分數／最新分數」全系統取代「基準／歷史／最新」；跨部門比較英文定案 Comparison Across Unit
- ⚡ **流程順化**：儲存追蹤計畫後直接進入詳情頁；詳情頁頁首精簡

### v5.5.0 新功能
- 🏢 **同期跨部門比較改版（純粹並列）**：跨部門計畫不再借用「基準→最新」視圖——每部門一張總覽卡、雷達圖 N 條線一部門一色、分數明細帶期別、02 頁籤改為「潛能差異」分組長條圖、次指標頁部門 × 次指標對照；**沒有基準、沒有標竿**，建立與管理流程同步移除相關欄位；頁首類型徽章清楚標示比較類型
- 🎨 **部門顏色固定**：同一部門在 HRI 頁與比較頁永遠同一顏色
- 🤖 **AI 助手 Q&A 引用同頁產出**：自然語言查詢可直接問「異常分析第三點」或「報告裡的建議」，回答與已生成內容一致
- 🔠 **全系統字級放大**：比較、HRI、AI 報告、問卷建立等頁面內文 +2px、最小 13px，適配桌面版顯示

### v5.4.0 新功能
- 🏥 **HRI 波次計算架構**：模組定名「醫院韌性指數 HRI」；從已儲存紀錄依波次（時間窗）聚合計算全院 HRI——跨波次混算在結構上不存在；HRI 數字旁強制並列涵蓋資訊（N 部門、M 份問卷），缺原始資料的部門以灰色列明確標示
- 📖 **Reference 方法論證據頁**：每個 HRI 數字帶著自己的正當性證明——方法依據表（CTT／ICC／等權 μσ 非補償性並陳）＋本波次證據（Cronbach's α、ICC(1)/(2) 兩層體檢、σ 旗標），判讀門檻預先定死
- 🔀 **比較流程整併**：資料總覽矩陣單一入口（韌性能力比較頁），橫列跨期比較與縱欄跨部門比較都就地開啟同一個「新增追蹤計畫」彈窗，分析共用同一套計畫詳情頁
- 🔍 **介面縮放**：帳號選單新增縮放控制（67%–150%），各台電腦記憶自己的設定，適配不同顯示器
- 🔒 **資安修復**：修復登入使用者可看到其他人專案的 RLS 政策問題（前端 owner 過濾＋資料庫修復腳本）
- 🌐 **術語統一**：respondent／Potential／Hospital Medicine Ward 全系統定案；RAG Analysis、問卷設計管理等模組更名

### v5.3.0 新功能
- 🏥 **HRI 模組更名「同時間不同部門比較」**：新增「各部門四潛能雷達比較」（各部門疊加同一張雷達圖）＋各部門平均值概念說明；「四潛能剖面」更名「四潛能雷達圖」
- 📈 **追蹤模組顯示強化**：差異摘要卡單行儀表板化（部門徽章、期別標籤、流動箭頭）、雷達比較改紅藍高對比、次指標「最弱／進步最多／退步最多」三清單、資料總覽期別欄凍結＋拖曳
- 🌐 **部門中英對照**：急診 Emergency Department、門診 Outpatient Department 等全名顯示，套用於全系統；「新增追蹤計畫」彈窗完整雙語化
- 📊 **RAG 分析頁**：基本資訊新增部門下拉（與存檔連動）、量表級距警示訊息
- 🐛 **修復**：PDF 報告首頁標題過長超出 A4（自動換行＋流動排版）

### v5.2.0 新功能（正式發布版）
- 🏥 **醫院韌性指數（HRI）方法學定案**：四層算術平均（題目→次指標→潛能→部門→全院）+ 各層 μ／σ，取代先前的加權／封頂設計；定位為描述性輪廓
- 🗂️ **HRI 資料總覽升級**：分析紀錄可刪除、自動推薦「同部門跨期」比較組合一鍵帶入、頁面動線重排
- 📊 **PDF 報告圖表重製**：雷達圖與菱形圖 900×720 置中高清輸出，修正匯出變形問題；Excel 匯出改為內建模組
- 📈 **韌性能力比較整併**：次指標雷達與明細合併為「韌性能力明細比較雷達圖」；中英文嚴格分離；「基準」欄一鍵設定基準；追蹤類型改為自由填寫的專案描述
- 🧠 **Gemini 模型更新**：預設 `gemini-3.6-flash`，可選 3.5 Flash / 3.1 Pro / 3.5 Flash-Lite，舊設定自動遷移
- 🎨 **介面細節**：主標題漸層流動文字、問卷發送步驟列微動畫、帳號選單全面中文化
- 🔒 **資安加固**：移除金鑰洩漏端點、CORS 同源限定、外開連結協定白名單、Supabase RLS 加固腳本、依賴漏洞 24 → 5
- 🐛 **修復**：Gmail 登入報錯、追蹤模組比較數據顯示錯誤、步驟切換空白等

### v5.0.0 新功能
- 🏥 **醫院韌性指數（HRRI）**：關鍵性加權非補償式彙總 + CFC 封頂，頭條分數／四能力雷達／科×能力熱區圖三件並陳
- ✉️ **問卷發送系統**：四步驟精靈、Excel 名單匯入與逐筆驗證、邀請信即時預覽、Resend 批次寄送＋測試信、信內 QR Code
- 📈 **韌性能力比較**：時間序列／跨部門／前後對比，Baseline 串接、雷達疊圖、差異卡、分數比較、趨勢圖
- ☁️ **雲端帳號與資料同步**：Google 登入、Supabase（RLS 權限隔離）雲端問卷管理、公開填答頁；未登入以 Demo 模式本機備援
- 🖥️ **桌面版重新上線**：Electron + NSIS 安裝精靈（IMDL RAG PRO Setup 5.0.0.exe）
- 🔐 **桌面版 Google 登入**：系統瀏覽器 + 本機 loopback（PKCE），避開內嵌瀏覽器封鎖
- 🏥 **醫療照護次指標全面更新**：依中英文總表重建 50 個次指標（五科），修正英文錯位與重複

### v4.2.0 新功能 🆕
- 🏥 **次指標系統（Sub-Indicators）**：內建 80+ 個醫療場域次指標，依部門（整合醫學病房、急診、AMU、內科、門診）與四大能力維度篩選，中英雙語定義
- 🤖 **AI 批次出題**：選取次指標後，透過自訂受測對象、聚焦方向、調查目的，一鍵批次生成 Likert 量表題目
- 🔔 **自動異常偵測**：資料載入後自動呼叫 Gemini API，偵測高標準差指標、低分維度、跨維度差異，以 Alert 提示卡呈現
- 💬 **AI 互動聊天**：Report Generator 頁新增聊天介面，可針對分析資料與 AI 即時對話
- 🌐 **架構轉移**：從 Electron 桌面 app 轉為 Express + Vite 全端網頁架構，執行更輕量（`npm run dev`）
- 📊 **長條圖摘要**：Results Report 新增四大潛能長條圖，一眼看出各維度相對強弱
- 🔤 **字體 CDN 載入**：PDF 中文字體改由 jsDelivr CDN 動態載入並快取，不再需要本地字型檔
- 🧠 **新 Gemini 模型**：新增 Gemini 3.1 Pro Preview、Gemini 3 Flash、Gemini 3.1 Flash-Lite 可選
  
### v4.1.0 新功能 🆕
- 📝 **問卷建立器全面升級**：專案式管理（Project → Version），支援版本控制與歷史追蹤
- 📚 **題庫系統（Question Bank）**：內建分類題庫，依產業（製造業、醫療、科技、金融）與維度篩選推薦題目
- 🤖 **AI 輔助出題**：透過自然語言描述自動生成問卷題目（整合 Gemini AI）
- 🔄 **版本生命週期**：支援 Draft → Published → Archived 完整發布流程
- 📄 **PDF 中文字體支援**：嵌入 NotoSansTC 字體，徹底解決中文亂碼問題
- 🔧 **AI 功能整合**：移除獨立 AI 助手頁面，統一整合至 Report Generator 模組
- 📊 **圖表 Props 修正**：修復 RadarCard 量表上限永遠為預設值 5 的 bug

### v4.0.0 新功能 
- 🌐 **中英文雙語介面**：一鍵切換中英文，全系統同步更新
- 🤖 **AI 助手**：內建 Google Gemini AI，支援自訂 API Key 與模型選擇
- 📊 **雷達圖優化**：分數直接顯示於各指標標籤旁
- 🎛️ **量表選項調整**：新增 3 點與 6 點量表，移除 10 點量表
- 🎨 **動態背景效果**：漸層色塊浮動動畫 + 毛玻璃介面效果
- 📁 **配置檔支援中文 Potential 名稱**：回應、監測、監控、預期、學習

### v3.2.0 新功能 
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
| ✅ 雲端同步 | 登入後問卷／分析／追蹤資料同步至 Supabase（RLS 權限隔離） |
| ✅ 離線備援 | 未登入時以本機 localStorage 暫存（Demo 模式） |
| ✅ 帳號登入 | Google 帳號登入（網頁彈窗 / 桌面系統瀏覽器） |
| ✅ 三級績效分類 | 更細緻的績效評估（紅/橘/綠） |
| ✅ 資料品質警告 | 自動偵測未定義的回答選項 |
| ✅ 中英文雙語介面 | 一鍵切換語言，全系統同步 |
| ✅ AI 助手 | 整合 Google Gemini，支援自訂 API Key |

---

## 🛠️ 技術亮點 | Technical Highlights

- 使用 **React 18 + TypeScript + Vite + Tailwind CSS 4** 打造
- **Express 5** 後端（開發整合 Vite middleware；桌面版由 Electron 內嵌）
- **Supabase**（Postgres + Auth + RLS）雲端資料與帳號，未登入以 localStorage 備援
- **Google Gemini（@google/genai）** 提供 AI 出題與報告
- **Recharts** 互動式圖表（雷達圖、菱形圖、熱區圖、趨勢圖）
- **jsPDF + jspdf-autotable + html2canvas** 專業 PDF 報告生成
- **SheetJS (xlsx)** Excel 匯入匯出
- **Electron + electron-builder** 打包 Windows 桌面安裝版（NSIS）

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

### Q: 我的資料存在哪裡？
**A:** 登入後，問卷、分析與追蹤資料儲存於 **Supabase 雲端**（受 RLS 權限保護，僅你本人可存取）；未登入時則以本機 localStorage 暫存（Demo 模式）。AI 出題／報告與 Google 登入需要網路連線。

### Q: 中英文如何切換？
**A:** 本版為單一應用程式，於帳號選單可一鍵切換繁體中文 / 英文，全系統（含 PDF 報告）同步切換，無需安裝不同語言版本。

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

### v5.6.0 (2026-08-31)
- 🧭 資料總覽兩步驟引導（選比較方式 → 動態指示）
- 📈 多部門趨勢分析（多部門一起跨期比較，無需初始分數）
- 🎨 跨期比較雷達圖：期別顯隱、高亮、自選線色
- 🏷️ 初始分數／中間分數／最新分數術語全系統統一
- ⚡ 儲存計畫直接進入詳情頁、頁首精簡

### v5.5.0 (2026-08-25)
- 🏢 同期跨部門比較改版為純粹並列比較（無基準／標竿），依部門固定配色
- 🤖 AI 助手 Q&A 可引用同頁異常分析與完整報告
- 🔠 全系統字級放大（內文 +2px、最小 13px）

### v5.4.0 (2026-08-16)
- 🏥 HRI 波次計算架構（同波次結構性保證＋涵蓋透明化＋缺測明確標示）
- 📖 Reference 方法論證據頁（方法依據＋α／ICC／σ 本波次體檢）
- 🔀 兩種比較流程整併為資料總覽單一入口
- 🔍 介面縮放功能（67%–150%，各機記憶）
- 🔒 修復跨使用者資料可見的 RLS 資安問題
- 🌐 respondent／Potential／Hospital Medicine Ward 術語全系統統一

### v5.3.0 (2026-08-15)
- 🏥 HRI 更名「同時間不同部門比較」＋各部門雷達疊加比較
- 📈 追蹤模組顯示強化（摘要卡重設計、紅藍對比雷達、資料總覽拖曳）
- 🌐 部門中英對照與追蹤彈窗完整雙語化
- 🐛 PDF 首頁標題跑版修正

### v5.2.0 (2026-08-12) - 正式發布版
- 🏥 HRI 方法學定案（四層算術平均 + μ/σ）
- 📊 PDF 圖表重製、Excel 匯出修復
- 📈 追蹤模組整併與中英文嚴格分離
- 🔒 打包前資安全面加固（依賴漏洞 24 → 5）

### v5.1.0 (2026-07-28)
- ✨ 互動式 WebGL 粒子背景
- ✏️ 「韌性能力追蹤」更名「韌性能力比較」

### v5.0.0 (2026-06-15)
- 🏥 醫院韌性指數（HRI）模組
- ✉️ 問卷發送系統（名單匯入、邀請信、批次寄送）
- 📈 韌性能力比較模組
- ☁️ 雲端帳號與資料同步（Supabase + Google 登入）
- 🖥️ Windows 桌面版重新上線（Electron）

### v4.0.0 (2026-03-17)
- 🌐 中英文雙語介面（i18n）
- 🤖 AI 助手（Google Gemini 整合）
- 📊 雷達圖標籤直接顯示分數
- 🎛️ 新增 3/6 點量表，移除 10 點量表
- 🎨 動態背景與毛玻璃效果

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

## 📦 舊版本 | Previous Versions

| 版本 | 下載 | 發布日期 |
|------|------|----------|
| v5.5.0 | [IMDL RAG PRO Setup 5.5.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v5.5.0/IMDL.RAG.PRO.Setup.5.5.0.exe) | 2026-08-25 |
| v5.4.0 | [IMDL RAG PRO Setup 5.4.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v5.4.0/IMDL.RAG.PRO.Setup.5.4.0.exe) | 2026-08-16 |
| v5.3.0 | [IMDL RAG PRO Setup 5.3.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v5.3.0/IMDL.RAG.PRO.Setup.5.3.0.exe) | 2026-08-15 |
| v5.2.0 | [IMDL RAG PRO Setup 5.2.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v5.2.0/IMDL.RAG.PRO.Setup.5.2.0.exe) | 2026-08-12 |
| v5.0.0 | [IMDL RAG PRO Setup 5.0.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v5.0.0/IMDL.RAG.PRO.Setup.5.0.0.exe) | 2026-06-15 |
| v3.2.0 中文版 | [RAG Resilience Analyzer Chinese Setup 3.2.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v3.2.0/RAG.Resilience.Analyzer.Chinese.Setup.3.2.0.exe) | 2026-02-08 |
| v3.2.0 英文版 | [RAG Resilience Analyzer Setup 3.2.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v3.2.0/RAG.Resilience.Analyzer.Setup.3.2.0.exe) | 2026-02-08 |

**⭐ 如果這個專案對您有幫助，請給我們一個 Star！**
**⭐ If this project helps you, please give us a Star!**

Made with ❤️ by [Hsuan-Hao Lo](https://github.com/x484838830)

