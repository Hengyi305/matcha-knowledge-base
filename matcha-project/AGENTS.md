# Matcha Knowledge Base - AI 協作與開發指南 (AGENTS.md)

## 1. 專案目的
本專案旨在建立一個「專業抹茶品鑑知識庫」。目標是讓使用者能快速查詢不同抹茶粉的產地、風味特徵、適用情境，以及正確的刷茶工具與參數。本文件用於指導 AI 在新增、修改網頁內容時，保持程式碼結構、視覺風格與資料格式的高度一致性。

## 2. 網頁整體風格 (Vibe & UI/UX)
*   **視覺風格：** 日系、極簡、禪意 (Zen-style)。
*   **色彩計畫：** 
    *   主色調：抹茶綠 (Matcha Green, `#8A9A5B` 或 `#4B5320`)
    *   背景色：米白色或和紙質感 (Off-white, `#FDFBF7`)
    *   文字色：深灰 (Dark Charcoal, `#333333`)
*   **排版：** 區塊分明，重視留白 (Whitespace)，適應 RWD 響應式設計。

## 3. 檔案與目錄結構
專案根目錄/
├── index.html          # 知識庫首頁 (包含所有抹茶款式的目錄清單與標籤篩選)
├── css/
│   └── style.css       # 共用樣式表
├── js/
│   └── main.js         # 互動邏輯 (如標籤篩選功能)
├── matcha_profiles/    # 存放個別抹茶介紹頁面的資料夾
│   ├── marukyu-isuzu.html
│   └── ... (未來新增的頁面)
└── AGENTS.md           # AI 協作規則文件

## 4. 檔案命名規則
*   所有新建的 HTML 頁面必須放在 `matcha_profiles/` 目錄下。
*   命名格式：`[品牌名稱]-[產品名稱].html`，全部使用小寫英文字母，並以連字號 `-` 分隔。
    *   *範例：丸久小山園的五十鈴 -> `marukyu-isuzu.html`*

## 5. 新增抹茶內容時的標準資料結構 (Data Schema)
當我要求「新增一款抹茶」時，請務必在生成的 HTML 結構中包含以下標籤與資訊區塊：
1.  **基本資訊：** 品牌名稱、產品名稱、產地 (如：京都宇治、福岡八女)。
2.  **風味標籤 (Tags)：** 旨味 (Umami) 等級 (1-5)、苦澀味 (Bitterness) 等級 (1-5)。
3.  **適用情境 (Context)：** 薄茶 (Usucha)、濃茶 (Koicha)、拿鐵 (Latte)、烘焙等。
4.  **標準沖煮參數：**
    *   粉量：(例如 2g)
    *   水量與水溫：(預設 70ml, 80°C)
    *   建議茶具：100本立茶筅、抹茶碗
    *   刷法提示：W/M字型刷法起泡，最後以「の」字型收尾。

## 6. AI 執行指令 (AI Instructions)
*   **Do not rewrite CSS:** 除非我特別要求修改整體排版，否則請直接套用原有的 `css/style.css` 類別名稱 (class names)。
*   **Template Matching:** 新增頁面時，請嚴格遵守上述第 5 點的資料結構，並使用 Semantic HTML (如 `<article>`, `<section>`, `<ul>`, `<span class="tag">`) 來構建。
*   **Language:** 網頁呈現內容必須為「繁體中文 (zh-TW)」。