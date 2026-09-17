# IMDL RAG PRO — RAG 韌性評估分析系統 | RAG Resilience Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-5.7.0-green.svg)](https://github.com/x484838830/RAG-Resilience-Analyzer)
[![TypeScript](https://img.shields.io/badge/TypeScript-97.5%25-blue.svg)](https://github.com/x484838830/RAG-Resilience-Analyzer)

> 組織韌性評估平台 | Organizational Resilience (RAG) Assessment Platform
> 
> 問卷設計、Google 表單建立與回收、批次發送、韌性能力分析、AI 報告、韌性能力比較與醫院韌性指數（HRI）；提供網頁版與 Windows 桌面版

---

## 📥 下載安裝 | Download

### 🌐 最新版本 | Latest Version

| 版本 | 下載 | 發布日期 |
|------|------|----------|
| **v5.7.0** | [IMDL RAG PRO Setup 5.7.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v5.7.0/IMDL.RAG.PRO.Setup.5.7.0.exe) | 2026-09-17 |
| **Analyzer** | [IMDL_RAG_Analyzer.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/IMDL_RAG_Analyzer/RAG.Analyzer.Setup.exe) | 2026-05-04 |

**系統需求 | System Requirements**：Windows 10/11 (64-bit)、4GB RAM、1000MB 硬碟空間

---

## ✨ 版本功能 | Version Features

### v5.7.0 新功能 🆕
- 📋 **問卷即定義檔**：韌性能力分析不再上傳設定檔——選「使用的問卷」，量表對照、四潛能與次指標對照、題序全部自動帶入；產業別、部門、量表級距標示「已自動帶入」；回覆檔題目起始欄自動偵測、預覽頁可微調；設定檔上傳降為「進階」（僅外部問卷需要）；已確定的問卷可「下載設定檔」
- 📝 **Google 表單一鍵建立與回收**：問卷預覽可直接在您的雲端硬碟建立 Google 表單（部門題＋全部題目，選項文字＝量表標籤）；問卷邀請一鍵帶入表單連結；韌性能力分析「從 Google 表單匯入」——取得回覆、選部門、匯入，題目欄位自動對齊、可另存 Excel；附「教學與說明」視窗與清楚的錯誤指引
- 🧭 **韌性能力比較參數化**：資料矩陣改為「趨勢分析／跨部門比較」兩張模式卡＋參數面板（部門多選＋期別範圍／期別＋部門勾選），資料再多也不會撐爆版面
- 🏥 **HRI 全面使用系統內資料**：移除上傳與示範資料；「計算 HRI」選期別勾部門即算，「HRI 趨勢分析」折線圖＋追蹤清單
- 🤖 **AI 整合進韌性能力分析**：結果頁「AI產生分析報告」＋「匯出AI分析報告 (PDF)」＋「向 AI 提問」問答彈窗；獨立 AI 頁面移除
- 🧪 **問卷數據異常分析**：確認欄位對應頁一鍵掃描原始作答（對不上量表的回答、整份同分、漏答、空白列），只提醒不阻擋
- 🏷️ **報告標題含部門**（組織 · 部門，網頁／PDF／Excel 同步）；「韌性能力資料存檔」、「分析圖表匯出 (PDF)」命名更清楚
- 🗂️ **比較紀錄清單化**：最新在上、依日期排序、附類型標籤；詳情頁標題改為「產業別-部門 類型」＋分析期間＋建立時間
- 🏥 **HRI 資料總覽矩陣**：計算 HRI 底部唯讀矩陣（部門 × 期別），固定 5 列、可捲動
- 🌐 **題目中英雙語自由切換**：AI 產題一次產出中英兩版；舊問卷一鍵「補齊中英文」；四潛能與次指標標籤同步翻譯
- ✏️ **問卷建立順化**：「建立新問卷」移至問卷建立頁並自動聚焦名稱欄；Likert 預設 5 點、可選 3～7 點；製造業次指標保留
- 🧠 **Gemini 3.8 Flash**：預設模型升級，可選 3.7 Flash / 3.1 Pro / 3.5 Flash-Lite，舊設定自動升級
- 🐛 **修復**：首次登入偶爾直接進入範例資料（範例資料不再寫入本機儲存）

### v5.6.0 新功能
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
| ✅ 問卷即定義檔 | 在系統確定的問卷即為分析定義，量表與題目對照自動帶入，不需設定檔 |
| ✅ Google 表單一鍵建立與回收 | 問卷預覽直接建立 Google 表單；回覆一鍵回收匯入分析 |
| ✅ 自動化問卷分析 | 上傳 Excel 回覆資料（或從 Google 表單匯入），自動計算分數 |
| ✅ AI 分析報告 | 描述、比較、標記值得關注之處的 AI 報告，可匯出 PDF |
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
| ✅ AI 助手 | 結果頁「AI產生分析報告」與「向 AI 提問」（Google Gemini，預設 3.8 Flash，支援自訂 API Key） |
| ✅ 韌性能力比較 | 趨勢分析（多部門跨期）與跨部門比較，參數式設定 |
| ✅ 醫院韌性指數 HRI | 依期別勾選部門計算全院 HRI，附趨勢分析與方法論證據頁 |

---

## 🛠️ 技術亮點 | Technical Highlights

- 使用 **React 18 + TypeScript + Vite + Tailwind CSS 4** 打造
- **Express 5** 後端（開發整合 Vite middleware；桌面版由 Electron 內嵌）
- **Supabase**（Postgres + Auth + RLS）雲端資料與帳號，未登入以 localStorage 備援
- **Google Gemini（@google/genai）** 提供 AI 出題、中英翻譯、異常分析與分析報告（預設 gemini-3.8-flash）
- **Google Forms API** 建立問卷表單與回收回覆（沿用 Supabase Google 登入授權）
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

### 2. 建立問卷與收集回覆 | Build the Survey & Collect Responses

1. **問卷建立**：建立問卷、AI 依次指標產題（中英雙語）、確定問卷。確定後的問卷版本就是分析定義，之後不需要另外的設定檔
2. **建立 Google 表單（選用）**：預覽問卷 → 「建立 Google 表單」→ 第一次允許 Google 授權 → 表單出現在您的雲端硬碟（第 1 題為部門，其後每題選項＝量表文字）。「複製填答連結」即可發送；「問卷邀請」也能直接帶入這個連結批次寄送
3. **回覆來源二選一**：
   - 從 Google 表單一鍵回收（韌性能力分析 → 「從 Google 表單匯入」）
   - 或整理成 Excel／CSV：第一個工作表、第一列為標題、每列一位受訪者；題目欄依問卷順序連續排列，前面可有時間戳記／信箱／部門等欄位；答案為量表文字（如「同意」）或 1～N 的數字

> ⚙️ **外部問卷才需要設定檔**：不是在本系統建立的問卷，可在「進階：自行上傳設定檔」提供四工作表格式（`Settings` 起始欄、`Likert_Mapping` 回答→分數、`Question_Mapping` 題目→Potential、`Colors` 選填），並可「下載空白設定檔範本」。

> 🔧 **Google 表單功能的一次性設定**（系統管理者）：在 Supabase Google 登入所用的 Google Cloud 專案啟用 Google Forms API、同意畫面加入 `forms.body` 與 `forms.responses.readonly`、測試模式下加入測試使用者；並在 Supabase SQL Editor 執行 `supabase/google_forms_migration.sql`。詳見 `docs/google-forms-integration.md` 與系統內「教學與說明」。

### 3. 分析流程 | Analysis Process

1. 進入「韌性能力分析」，輸入組織／報告標題
2. 步驟二選「使用的問卷」——產業別、量表級距自動帶入，四潛能題數即時顯示
3. 提供回覆資料：上傳 Excel／CSV，或「從 Google 表單匯入」（選部門後匯入，部門與期別自動帶入）
4. 點「下一步」：預覽頁確認題目起始欄（自動偵測，可 −／＋ 微調）與對照片段；可按「問卷數據異常分析」先檢查原始作答有沒有問題（只提醒，不阻擋）
5. 查看四個雷達圖、菱形圖與各題統計；調整圖表外觀；報告標題為「組織 · 部門」
6. 「分析圖表匯出 (PDF)」「匯出分析結果 (Excel)」、「AI產生分析報告」→「匯出AI分析報告 (PDF)」，或「向 AI 提問」直接針對結果問答
7. 「韌性能力資料存檔」後可在「韌性能力比較」進行跨期／跨部門比較，並在「醫院韌性指數 HRI」依期別計算全院 HRI

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

### Q: 建立 Google 表單時顯示「尚未啟用 Google Forms API」或「沒有拿到表單權限」？
**A:** 這是系統管理者的一次性設定還沒完成，與使用者操作無關。請到 Supabase Google 登入所用的 Google Cloud 專案啟用 Google Forms API（訊息裡有「前往啟用」連結），並確認同意畫面已加入表單權限、您的帳號在測試使用者清單中。啟用後等 1～2 分鐘直接再按一次即可。系統內的「教學與說明」有完整步驟。

### Q: 回覆 Excel 要長什麼樣子才能分析？
**A:** 第一個工作表、第一列為標題、每列一位受訪者；題目欄依問卷順序連續排列，前面可以有時間戳記、信箱、部門等欄位；答案為量表文字（例如「同意」）或 1～N 的數字。系統會依問卷第一題文字自動定位起始欄，預覽頁可再微調。從 Google 表單匯入則完全不需整理。

### Q: 如何自訂圖表顏色？
**A:** 僅外部問卷的設定檔流程支援：在配置檔中新增 `Colors` 工作表，格式如下：
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

### v5.7.0 (2026-09-17)
- 📋 問卷即定義檔：韌性能力分析不再上傳設定檔，對照自動帶入（產業別／部門／量表級距標示已自動帶入）
- 📝 Google 表單一鍵建立、問卷邀請帶入連結、回覆一鍵回收匯入；教學與說明視窗
- 🧭 韌性能力比較改為模式卡＋參數面板；比較紀錄清單化；詳情頁標題「產業別-部門 類型」
- 🏥 HRI 移除上傳與示範資料，改為「計算 HRI」（附唯讀資料總覽矩陣）與「HRI 趨勢分析」
- 🤖 AI 產生分析報告（可匯出 PDF）與向 AI 提問整合進韌性能力分析結果頁；獨立 AI 頁面移除
- 🧪 確認欄位對應頁新增問卷數據異常分析；報告標題含部門；韌性能力資料存檔、分析圖表匯出 (PDF) 更名
- 🌐 題目中英雙語跟著介面切換、一鍵補齊中英文
- ✏️ 建立新問卷移至問卷建立頁、Likert 3～7 點可選
- 🧠 Gemini 預設升級 3.8 Flash
- 🐛 修復首次登入直接進入範例資料

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
| v5.6.0 | [IMDL RAG PRO Setup 5.6.0.exe](https://github.com/x484838830/RAG-Resilience-Analyzer/releases/download/v5.6.0/IMDL.RAG.PRO.Setup.5.6.0.exe) | 2026-08-31 |
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

