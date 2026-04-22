# 更新日誌

本專案的所有重要更改都將記錄在此檔案中。
---

## [4.2.0] - 2026-04-22

### 🎉 重大功能更新

#### 次指標系統（Sub-Indicators）
- **全新醫療場域次指標資料庫**：內建 80+ 個次指標，涵蓋 Response、Monitor、Anticipate、Learn 四大能力維度
- **部門篩選**：支援整合醫學病房（IMW）、急診（ED）、AMU、內科（IM）、門診（OPD）五個部門分類
- **中英雙語定義**：每個次指標附有完整英文 definition 與中文 definition_zh
- **新資料檔 `data/subIndicators.ts`**：統一管理次指標與部門選項，提供 `getSubIndicators()` 與 `getDepartments()` 工具函式

#### AI 批次出題
- 勾選次指標後點擊「AI 出題」，開啟設定 Modal
- 可自訂三個生成參數：受測對象（如「第一線現場人員」）、聚焦方向（如「實際執行情形」）、調查目的（選填）
- AI 根據次指標定義、產業、部門、Likert 量表標籤，批次生成 Likert 題目並自動排除已有題目的次指標
- 語言跟隨系統設定自動切換（繁中 / 英文）

#### 自動異常偵測
- 資料載入 Report Generator 後，自動呼叫 Gemini API 分析數據
- 偵測項目：高標準差指標（> 1.0）、低分維度、跨維度顯著差異
- 偵測結果以 Alert 提示卡列表方式顯示於頁面頂端
- 支援錯誤回退：503（模型過載）/ 404（模型不存在）/ API Key 無效各有對應提示訊息

#### AI 互動聊天（Report Generator）
- Report Generator 頁新增聊天介面，可針對當前分析資料與 AI 即時問答
- 對話記錄保存於 session，支援捲動至最新訊息
- 分析數據摘要自動作為 context 傳入每次對話

### ✨ 功能改進

#### 架構轉移：Electron → Express + Vite
- 移除 Electron、electron-builder、concurrently、cross-env、wait-on 相依套件
- 新增 `server.ts`：Express 5 後端伺服器，整合 Vite dev server（開發時 HMR 支援）
- 新增 cors、dotenv、express、tsx 相依套件
- 執行指令由 `npm run dev:web / dev:desktop` 統一改為 `npm run dev`（`tsx server.ts`）
- 移除 `electron/main.cjs` 與 electron-builder 打包設定

#### Results Report — 長條圖視覺化
- 新增四大潛能得分長條圖（BarChart），使用 Recharts BarChart + LabelList
- 各 bar 以對應潛能顏色填色，懸停顯示分數 tooltip

#### PDF 字體載入優化
- 中文字體改由 jsDelivr CDN（`cdn.jsdelivr.net/gh/googlefonts/noto-fonts`）動態載入
- 實作 `cachedFontBase64Promise` 全域快取，同一 session 僅下載一次（約 7MB）
- 移除舊版需要本地 `fonts/NotoSansTC-Regular.ttf` 的載入邏輯

#### AI 模型選項更新
- 新增可選模型：`gemini-3.1-pro-preview`、`gemini-3-flash`、`gemini-3.1-flash-lite`
- 新增繁中說明：最強推理能力 / 多模態理解 / 最低成本低延遲

#### Report Generator AI 分析強化
- 移除原有 `/api/ai/generate-report` API 呼叫，改為前端直接呼叫 Gemini SDK
- 強化分析提示詞：加入「摘要開頭 2-3 句」、「數字呈現更直覺（用排名 / 百分比）」、「高標準差先結論後列表」等輸出規範
- 嚴格禁止 AI 下結論、給改善建議、做因果推論

#### SurveyBuilder 重構
- 移除舊版 Question Bank（Supabase 來源）、Dimension 篩選、AI 助手 tab
- 移除 `INDUSTRY_PRIORITIES` 硬編碼常數
- 新增「清除所有題目」功能，需確認對話框才執行
- 修正 AI 產出語言：預設值隨系統語言切換同步更新

### 🐛 錯誤修復
- 修復 `DiamondChart` 未接收 `scale_points` prop 導致計算錯誤的問題
- 修復 `ResultsReport` 中 `useRef` 未正確清理的潛在記憶體問題
- 修復 `html2canvas-pro` → `html2canvas 1.4.1`（版本相容性問題）

### ⚠️ 重大變更
- **SurveyBuilder 舊版 Question Bank 功能移除**：改由次指標系統取代
- **`/api/ai/generate-report` 端點移除**：AI 功能改為前端直接呼叫

---
## [4.1.0] - 2026-04-04

### 🎉 重大功能更新

#### 問卷建立器全面升級（Survey Builder V2）
- **專案式管理**：問卷採用 Project → Version 架構，支援版本控制與歷史追蹤
- **題庫系統（Question Bank）**：內建分類題庫，依產業（製造業、醫療、科技、金融）與維度篩選推薦題目
- **AI 輔助出題**：整合 Gemini AI，可透過自然語言描述自動生成問卷題目（例如：「我想評估遠端工作的資安意識」）
- **版本發布流程**：支援 Draft → Published → Archived 完整生命週期
- **量表範本系統**：預設支援 3/5/6 點 Likert 量表，一鍵套用

#### AI 功能整合重構
- **合併 AIAssistant 至 ReportGenerator**：移除獨立的 AI 助手頁面，將異常偵測、自然語言 Q&A、完整報告生成統一整合至「Report Generator」模組
- 採用 `AISettingsContext` 集中管理 API Key 與模型設定
- 側邊欄導航統一指向 `/report-generator`，消除路由不一致問題

### ✨ 功能改進

#### PDF 匯出中文支援
- **NotoSansTC 中文字體**：PDF 報告全面支援中文顯示，解決 `helvetica` 字體中文亂碼問題
- 字體檔案採用 base64 快取機制，避免重複下載
- 所有 autoTable 表格（含 header、body、didParseCell）統一套用中文字體

#### 圖表庫升級
- `html2canvas` 升級為 `html2canvas-pro`，移除 `@ts-ignore` 標記
- `jsPDF` 改為正確的 named import（`{ jsPDF }`）

#### 圖表 Props 修正
- 修正 RadarCard 元件 prop 名稱：`scale_points` → `maxScale`（修復量表上限永遠為預設值 5 的 bug）
- 移除 DiamondChart 不存在的 `scale_points` prop

### 🔧 技術細節
- 新增 `vite-env.d.ts` 提供 `.ttf?url` 模組的 TypeScript 型別宣告
- 新增 `lib/api.ts` API 服務層，支援 Supabase（雲端）與 Local（Demo）雙模式
- 新增 `lib/scales.ts` 量表範本定義
- 新增 `lib/demoResults.ts` Demo 模式假資料
- 刪除 `pages/AIAssistant.tsx`（功能已合併至 ReportGenerator）

### ⚠️ 重大變更
- AI 助手頁面（`/ai-assistant`）已移除，所有 AI 功能統一由 Report Generator（`/report-generator`）提供
- 問卷建立器完全重構，從單一表單改為專案式題庫架構

## [4.0.0] - 2026-03-17

### 🎉 重大功能更新

#### 多語言介面支援（i18n）
- 新增中英文介面切換功能，全系統所有靜態文字均支援雙語切換
- 建立 `locales/en.json` 與 `locales/zh.json` 語系檔
- 新增 `LanguageContext` 全域語言狀態管理
- Excel 配置檔的 Potential 欄位現支援中文輸入（回應、監測、監控、預期、學習）

#### AI 助手功能
- 新增內建 AI 助手頁面，整合 Google Gemini 模型
- 支援使用者自訂 Gemini API Key（留空則使用系統預設）
- 提供模型選擇下拉選單（Gemini 3 Flash Preview、Gemini 3.1 Pro Preview、Gemini 3.1 Flash Lite Preview）
- API Key 與模型選擇自動儲存至 localStorage，下次開啟免重填
- AI 助手介面完整支援中英文切換

### ✨ 功能改進

#### 雷達圖優化
- 指標分數直接顯示於雷達圖頂點標籤旁，無需對照底部表格
- 分數文字顏色自動對應各 Potential 主題色
- 智慧標籤偏移機制，避免文字遮擋圖表網格
- 移除雷達圖底部的 Legend 對照表格，版面更簡潔

#### 問卷量表選項調整
- 新增 3-Point Scale（不同意、普通、同意）
- 新增 6-Point Scale（非常不同意至非常同意）
- 移除 10-Point Scale

#### 報告與統計表格
- 移除 Detailed Item Scores 區塊，報告版面更精簡
- Descriptive Statistics 表格新增欄位排序功能（點擊標題即可排序）
- 預設依照 Focus 欄位字母順序排列
- PDF 匯出按鈕文字支援中英文切換

### ✨ 視覺改進

#### 動態背景效果
- 全系統加入動態漸層色塊背景（含緩慢漂浮動畫）
- 側邊欄與內容區塊加入毛玻璃效果（Backdrop Blur）
- 受測者公開填答頁面同步套用動態背景

### 🔧 技術細節
- 新增 `AnimatedBackground` 元件統一管理動態背景
- 新增 `pages/` 資料夾，拆分 SurveyBuilder、ExcelAnalysis、AIAssistant、SurveyPublic 頁面
- `context/LanguageContext.tsx` 提供全域語言狀態

### ⚠️ 重大變更
- 系統架構重組，新增 `pages/`、`context/`、`locales/` 資料夾
- 原規劃於 v3.1.0 的多語言支援與雷達圖優化提前實作並一併納入本版本
- 原規劃於 v4.0.0 的 AI 功能提前實作

---
## [3.2.0] - 2026-02-08

### 🎉 新功能

#### 圖表外觀自訂
- 🎨 **主題色票選擇**：提供 5 種預設色票
  - 預設（標準）/ Default (Standard)
  - 專業（深色）/ Professional (Deep)
  - 鮮豔（霓虹）/ Vivid (Neon)
  - 柔和（粉彩）/ Pastel (Soft)
  - 企業（灰藍）/ Corporate (Grayscale/Blue)
- 📏 **線條粗細調整**：可調整雷達圖與菱形圖的線條粗細（1px - 6px）
- 🔆 **透明度調整**：可調整圖表填充區域的透明度（10% - 100%）
- 📁 **自訂顏色支援**：可在配置檔新增 `Colors` 工作表自訂各 Potential 顏色

#### Excel 匯出功能
- 📊 **匯出分析資料**：新增「匯出資料 (Excel)」按鈕
- 匯出內容包含兩個工作表：
  - **執行摘要**：整體分數、四個潛能分數、受訪者人數
  - **詳細資料**：每題的潛能、焦點項目、平均分數、狀態、標準差、最小/最大值、樣本數

#### 表格排序功能
- 🔀 **可排序表格**：「詳細項目分數」表格支援點擊標題排序
- 可依「潛能」、「焦點項目」、「平均分數」排序
- 預設依分數由低到高排列，方便快速找出弱項

#### 組織名稱輸入
- 🏢 **報告標題自訂**：新增「組織名稱 / 報告標題」輸入欄位
- 輸入的名稱會顯示在報告標題、PDF 報告、Excel 匯出檔案中

### ✨ 功能改進

- 圖表外觀控制面板整合於結果頁面上方
- PDF 與 Excel 匯出按鈕並列顯示
- 配置範本新增 `Colors` 工作表範例

### 🔧 技術細節
- 新增 `ChartSettings` 介面定義圖表樣式參數
- `SurveyConfig` 新增 `colors` 欄位支援自訂顏色
- `RadarCard` 與 `DiamondChart` 元件接收 `settings` props
- 使用 `useMemo` 優化表格排序效能

---

## [3.1.0] - 2026-01-28 (中文版 Chinese Version)

### 🎉 重大功能更新

#### 完整中文介面
- 🌐 **全介面中文化**：所有按鈕、標籤、提示訊息皆為繁體中文
- 📄 **中文 PDF 報告**：匯出的 PDF 報告完整支援中文顯示
- 🔤 **嵌入 Noto Sans TC 字體**：解決 PDF 中文亂碼問題

#### 中英文配置檔支援
- 🔄 **雙語 Potential 支援**：配置檔可使用中文或英文的 Potential 名稱
- 自動轉換對應關係，無需修改程式碼

### 📋 Potential 名稱對照表

| 中文 | 英文 |
|------|------|
| 回應 | Response |
| 監控 | Monitor |
| 預測 | Anticipate |
| 預見 | Anticipate |
| 學習 | Learn |

### ✨ 功能改進

- 配置範本更新為中文範例
- 錯誤訊息全面中文化
- PDF 報告頁首/頁尾顯示中文日期格式

### 🔧 技術細節
- 新增 `fonts/notoSansTCFont.ts` 字體模組（約 9.6MB）
- 修改 `ResultsReport.tsx` 註冊並使用中文字體
- 修改 `App.tsx` 加入中英文 Potential 對照表

---

## [3.0.0] - 2026-01-20

### 🎉 重大功能更新

#### PDF 匯出功能全面革新
- **完整重新設計** PDF 報告生成系統，採用混合式方法（html2canvas + jspdf-autotable）
- **專業多頁面配置**：
  - 第 1 頁：執行摘要，包含放大的菱形圖與關鍵潛能分數
  - 第 2-5 頁：個別潛能詳細分析（Response、Monitor、Anticipate、Learn 各一頁），含雷達圖
  - 後續頁面：完整統計表格，支援自動分頁
- **視覺設計強化**：
  - 雷達圖加入圓角背景框
  - 潛能指標採用顏色編碼（Response 藍色、Monitor 紅色、Anticipate 橘色、Learn 綠色）
  - 每頁均有一致的頁首/頁尾，顯示日期與頁碼

### ✨ 功能改進

#### 評分與分析
- **三級績效分類系統**：
  - 🔴 **需要改進**（< 3.0）：紅色指標
  - 🟠 **中等表現**（3.0 - 3.9）：橘色指標
  - 🟢 **表現良好**（≥ 4.0）：綠色指標
- 更準確的狀態評估，符合李克特量表（Likert Scale）語意

#### 資料品質管控
- **資料品質警示系統強化**：自動偵測並報告未定義的問卷回應
- 採用 HTML 快照方法避免字元編碼問題
- 偵測到資料品質問題時，在報告首頁顯示視覺化警告框（黃色警告卡片）

#### 技術優化
- **動態內容適應**：穩健處理每個潛能不同數量的焦點項目
- **智慧分頁**：表格自動分頁，避免內容被截斷
- **錯誤處理改進**：截圖失敗時的優雅降級機制
- **圖表圖例**：每個潛能頁面均附評分標準說明文字

### 🐛 錯誤修復
- 修復表格在分頁處被切斷的問題
- 解決 PDF 文字渲染的字元編碼問題（中文顯示亂碼）
- 改善雷達圖標籤可見度

### 🔧 技術細節
- 新增 `jspdf-autotable` 相依套件用於原生 PDF 表格生成
- 實作隱藏 DOM 容器以進行乾淨的 HTML 轉圖片轉換
- 優化畫布渲染設定以提升圖片品質（scale: 2）

### ⚠️ 重大變更
- PDF 結構完全重組（從單頁截圖改為多頁專業報告）
- 描述性統計表格移除中位數（Median）與眾數（Mode）欄位
- 評分標準從二級制改為三級制

---

## [2.0.0] - 2026-01-15

### 🎉 重大功能更新

#### Windows 桌面應用程式
- 🖥️ 新增獨立的 Windows 安裝檔（.exe）
- 使用 Electron 框架打包，支援離線使用
- 無需安裝 Node.js 或其他開發工具

#### 資料警告系統
- ⚠️ 新增資料警告功能：自動偵測並顯示無法匹配的回答選項
- 無法識別的回答會被排除計算，並在介面上方顯示黃色警告區塊
- 使用者可根據警告內容更新配置檔

### ✨ 功能改進

#### 計算邏輯優化
- 計算邏輯完全依賴設定檔（移除所有寫死的關鍵字）
- Likert 分數匹配改為不區分大小寫
- 支援更彈性的回答選項配置

### 🐛 錯誤修復
- 修復部分回答選項無法正確識別的問題
- 修復雷達圖 Tooltip 顯示 "1.1 - 1.1.Event List" 重複編號的問題

### 💻 系統需求
- Windows 10 / 11 (64-bit)
- 4GB RAM 以上
- 500MB 硬碟空間

---

## [1.0.0] - 2026-01-02

### 🎉 首次發布

#### 核心功能
- ✅ **問卷資料分析**：支援上傳 Excel/CSV 格式的問卷資料
- ✅ **配置檔系統**：透過 Excel 配置檔定義 Likert 對應與題目結構
- ✅ **四個 Potential 分析**：
  - Response（回應）
  - Monitor（監控）
  - Anticipate（預見）
  - Learn（學習）

#### 視覺化功能
- 📊 **雷達圖**：每個 Potential 生成獨立的雷達圖
- 💎 **菱形圖**：顯示四個 Potential 的面積占比與整體韌性分數
- 📈 **統計表格**：顯示各項目的平均分數、標準差等統計數據

#### 報告匯出
- 📄 **PDF 匯出**：一鍵下載完整分析報告

#### 技術特點
- 🌐 基於 React + TypeScript + Vite 開發
- 📱 響應式設計，支援桌面與行動裝置
- 🔒 完全在瀏覽器本地端運算，資料不上傳雲端

---

### 更新類型圖示

| 圖示 | 說明 |
|------|------|
| 🎉 | 重大功能更新 |
| ✨ | 功能改進 |
| 🐛 | 錯誤修復 |
| 🔧 | 技術細節 |
| ⚠️ | 重大變更 |
| 🔒 | 安全性更新 |
| 📊 | 效能改進 |
| 📚 | 文件更新 |

---

## 問題回報

發現 Bug 或有功能建議？歡迎在 [GitHub Issues](https://github.com/x484838830/RAG-Resilience-Analyzer/issues) 提出！
