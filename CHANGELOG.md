# 更新日誌 | Changelog

本專案的所有重要更改都將記錄在此檔案中。

---

## [5.0.0] - 2026-06-15

> 自 4.2.0 以來累積的重大版本：新增「問卷發送」「韌性能力追蹤」「醫院韌性指數」三大模組、導入雲端帳號與資料同步，並以 Electron 重新推出 Windows 桌面安裝版。

### 🎉 重大功能更新

#### 問卷發送系統（Assessment Invitation）
- 四步驟精靈：基本資訊 → 收件名單 → 邀請信 → 確認寄送
- Excel / CSV 收件名單匯入，自動辨識欄位並逐筆驗證（錯誤 / 警告標示，可線上檢視、編輯與勾選）
- 邀請信編輯器 + 即時信件預覽，支援動態變數（收件者姓名、職稱、問卷名稱、問卷連結、截止日期、發送單位…）
- 經 Supabase Edge Function（Resend）批次寄送，可先寄「測試信」確認排版
- 信件內含「開始填答」按鈕與 QR Code

#### 韌性能力追蹤（Resilience Tracking）
- 三種追蹤型態：時間序列（time series）、跨部門（cross department）、前後對比（before / after）
- 以 Baseline 基準點串接多筆分析紀錄，建立追蹤計畫
- 視覺化：雷達疊圖、四能力與次指標雷達、差異摘要卡、分數比較表、維度趨勢圖、次指標總覽
- 資料一致性提醒：混合量表 / 版本、低樣本數（< 10）自動警示

#### 醫院韌性指數（HRRI）
- 全新頁面：以**關鍵性加權非補償式彙總**計算單一治理分數
- 計算層 `utils/hrri.ts`（純 TypeScript、完整型別）：標準化（Hollnagel 0–4 → 0–100，含正值地板 raw 0→20）、跨科加權幾何平均、CFC 封頂（最弱關鍵科低於門檻則全院封頂）
- 視覺化：頭條分數 + 四能力雷達 +（科 × 能力）熱區圖三件並陳，可切換健康 / 失效情境
- CFC 門檻設為 60（對應 Hollnagel raw 2.0 = Acceptable）

#### 雲端帳號與資料同步（Supabase）
- Google 帳號登入（OAuth）；`profiles` 個人資料、`survey_projects / survey_versions / survey_version_questions` schema，並以 RLS 做使用者資料隔離
- 「問卷管理」雲端化：草稿 / 發布 / 封存、搜尋、分頁、版本管理
- 公開問卷填答頁（Survey Public）：受訪者免登入填答、匿名 ID、裝置偵測，回覆寫入雲端
- 未登入 / 未設定雲端時，以 localStorage **Demo 模式**自動備援（`ProxyApiService` 動態切換）

#### 桌面版重新上線（Electron + NSIS 安裝程式）
- 重新提供 **Windows 桌面安裝版**：`IMDL RAG PRO Setup 5.0.0.exe`（NSIS 安裝精靈，桌面 / 開始選單捷徑）
- Electron 內嵌 Express 後端（API + 靜態 SPA），`electron-builder` 打包，鑽石 logo 圖示
- `server.ts` 重構為 `createApiApp()` / `createDesktopApp()`，桌面與網頁共用後端邏輯

#### 桌面版 Google 登入（OAuth）
- 桌面版改用**系統預設瀏覽器 + 本機 loopback** 完成 Google 登入，避開 Google 對內嵌瀏覽器的封鎖
- Supabase 改用 **PKCE flow**，授權碼以 `?code=` 帶回供 loopback 接收；網頁彈窗流程同樣相容

### ✨ 功能改進

#### 醫療照護次指標全面更新
- 依權威中英文總表（Excel）重建 Healthcare 次指標，共 **50 個唯一次指標**，涵蓋內科 / 急診 / 整合醫學病房 / 重症病房 / 門診五科
- 每個次指標含正確的中英文名稱、定義與科別歸屬；修正先前「預期」維度英文名稱錯位、移除重複次指標

#### 問卷發送修正
- 測試信改用名單中第一位真實收件者代入（原本寫死「王小明」）
- 即時預覽與實寄一致：姓名空白即顯示空白，不再以範例資料誤導

### 🐛 錯誤修復
- 修正 Express 5 不支援 `'*'` 萬用路由導致的伺服器啟動錯誤（改用 middleware fallback）
- 移除未使用且變數名不一致的死檔 `utils/email/emailTemplateRenderer.ts`

### ⚠️ 重大變更
- **重新提供 Windows 安裝版 (.exe)**（[4.2.0] 曾移除，本版以 Electron 重新導入）
- 導入**雲端帳號制**：雲端問卷管理 / 追蹤 / 發送需 Google 登入；未登入仍可用 Demo 模式本機試用
- Supabase 驗證流程由 implicit 改為 **PKCE**

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
- **不再提供 Windows 安裝版 (.exe)**：架構已轉為網頁，需 Node.js 18+ 執行
- **SurveyBuilder 舊版 Question Bank 功能移除**：改由次指標系統取代
- **`/api/ai/generate-report` 端點移除**：AI 功能改為前端直接呼叫

---

## [4.1.0] - 2026-04-04

### 🎉 重大功能更新

#### 問卷建立器全面升級
- **專案式管理**：Survey 重命名為 Project，以 Project → Version 兩層結構管理問卷
- **版本生命週期**：Draft → Published → Archived 完整流程，Published 版本鎖定不可修改
- **版本複製**：可從現有版本建立新版本，保留題目快照

#### 題庫系統（Question Bank）
- 內建分類題庫（`data/questionBank.ts`）：20 題，涵蓋 General / Healthcare / Manufacturing / Technology / Finance 五個產業
- 依產業與維度篩選推薦題目，優先顯示符合當前專案產業的題目

#### AI 輔助出題
- 透過自然語言描述自動生成問卷題目（整合 Gemini AI）
- 支援按維度出題，生成結果可直接加入草稿版本

### ✨ 功能改進
- 版本管理介面：新增版本狀態標籤、發布 / 封存操作按鈕
- Share Link：Published 版本可複製公開連結，受訪者直接填答

### 🐛 錯誤修復
- 修復 `RadarCard` 量表上限永遠為預設值 5 的 bug（`scale_points` prop 未正確傳遞）
- 修復 AI 助手頁面移除後路由殘留問題

---

## [4.0.0] - 2026-03-17

### 🎉 重大功能更新

#### 中英文雙語介面（i18n）
- 全系統支援繁體中文 / 英文切換，包含所有按鈕、標籤、提示訊息、PDF 報告
- 語言設定持久化於 localStorage
- 新增 `locales/en.json` 與 `locales/zh.json` 翻譯檔，以 `useLanguage()` hook 存取

#### AI 助手（Google Gemini 整合）
- 內建 Gemini AI 助手頁面，支援自訂 API Key 與模型選擇（`gemini-2.0-flash` 等）
- `AISettingsContext` 管理 API Key、模型、設定視窗開關
- AI Settings Modal 獨立元件，可從任意頁面開啟

#### 動態背景效果
- `AnimatedBackground` 元件：漸層色塊浮動動畫 + 毛玻璃介面效果
- 各頁面背景主題色跟隨內容動態調整

### ✨ 功能改進
- 雷達圖標籤直接顯示分數（不需懸停 tooltip）
- 新增 3 點與 6 點量表模板，移除 10 點量表
- 配置檔支援中文 Potential 名稱（回應、監測、預期、學習）

---

## [3.2.0] - 2026-02-08

### ✨ 功能改進

#### 圖表外觀自訂
- 可選擇 5 種主題色票（Default / Ocean / Forest / Sunset / Mono）
- 調整雷達圖線條粗細（1–5px）與填色透明度
- 自訂設定即時套用，無需重新分析

#### 匯出功能強化
- 新增 Excel 匯出：一鍵匯出含統計摘要的 Excel 檔案
- 組織名稱輸入欄位，顯示於 PDF 標題與 Excel 頁首

#### 表格操作
- 結果表格支援點擊標題欄位排序（升冪 / 降冪）
- 可快速找出各 Potential 中的弱項指標

### 🐛 錯誤修復
- 修復自訂顏色配置（`Colors` 工作表）無法正確讀取的問題

---

## [3.1.0] - 2026-01-28

### ✨ 功能改進

#### 完整中文介面
- 所有按鈕、標籤、提示訊息改為繁體中文
- 匯出的 PDF 報告完整支援中文顯示
- 嵌入 Noto Sans TC 字體至應用程式包（7.1MB），解決中文 PDF 亂碼問題

#### 配置檔中英文相容
- `Question_Mapping` 工作表 Potential 欄位可使用中文（回應、監控、預見、學習）或英文

---

## [3.0.0] - 2026-01-20

### 🎉 重大功能更新

#### PDF 匯出功能全面革新
- **完整重新設計**：採用混合式方法（html2canvas + jspdf-autotable）
- **多頁面配置**：
  - 第 1 頁：執行摘要（菱形圖 + 關鍵潛能分數）
  - 第 2–5 頁：個別潛能詳細分析（含雷達圖）
  - 後續頁：完整統計表格（自動分頁）
- **視覺強化**：顏色編碼指標、一致頁首 / 頁尾、日期與頁碼

### ✨ 功能改進
- **三級績效分類**：🔴 需要改進（< 3.0）/ 🟠 中等表現（3.0–3.9）/ 🟢 表現良好（≥ 4.0）
- **資料品質警示**：自動偵測未定義回答選項，於報告首頁顯示黃色警告卡片
- **智慧分頁**：表格自動分頁，避免內容截斷

### 🐛 錯誤修復
- 修復表格在分頁處被切斷的問題
- 解決 PDF 文字渲染的字元編碼問題

### ⚠️ 重大變更
- PDF 結構完全重組（從單頁截圖改為多頁專業報告）
- 評分標準從二級制改為三級制

---

## [2.0.0] - 2026-01-15

### 🎉 重大功能更新

#### Windows 桌面應用程式
- 新增獨立 Windows 安裝檔（.exe），使用 Electron 框架打包
- 支援完全離線使用，無需安裝 Node.js

#### 資料警告系統
- 自動偵測並顯示無法匹配的回答選項
- 無法識別的回答排除計算，介面顯示黃色警告區塊

### ✨ 功能改進
- 計算邏輯完全依賴設定檔（移除所有寫死關鍵字）
- Likert 分數匹配改為不區分大小寫

### 🐛 錯誤修復
- 修復部分回答選項無法正確識別的問題
- 修復雷達圖 Tooltip 顯示 "1.1 - 1.1.Event List" 重複編號的問題

---

## [1.0.0] - 2026-01-02

### 🎉 首次發布

#### 核心功能
- 問卷資料分析：支援上傳 Excel 格式問卷資料
- 配置檔系統：透過 Excel 配置檔定義 Likert 對應與題目結構
- 四個 Potential 分析：Response / Monitor / Anticipate / Learn

#### 視覺化功能
- 雷達圖（每個 Potential 獨立呈現）
- 菱形圖（四個 Potential 面積占比與整體韌性分數）
- 統計表格（平均分數、標準差等）

#### 報告匯出
- PDF 匯出：一鍵下載完整分析報告

---

## 更新類型圖示

| 圖示 | 說明 |
|------|------|
| 🎉 | 重大功能更新 |
| ✨ | 功能改進 |
| 🐛 | 錯誤修復 |
| 🔧 | 技術細節 |
| ⚠️ | 重大變更 |
| 🔒 | 安全性更新 |

---

## 問題回報

發現 Bug 或有功能建議？歡迎在 [GitHub Issues](https://github.com/x484838830/RAG-Resilience-Analyzer/issues) 提出！
