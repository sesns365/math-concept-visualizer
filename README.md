# 數學概念動態表徵介面小幫手（math-concept-visualizer）

專為資源班教師打造的 Claude skill。告訴它一個國小數學概念，就會依特教 CRA（具體—半具體—抽象）教學歷程，做出一個隨開即用的 HTML 互動教材。

由特工365 製作，改編自 [https://mathematics-classroom-of-tr-liang.github.io/copy-a-new-gem-setting/](https://mathematics-classroom-of-tr-liang.github.io/copy-a-new-gem-setting/)。

**線上試用範例教材**：https://sesns365.github.io/math-concept-visualizer/demo.html （二位數進位加法）

## 每份教材都有三種模式

- **教學探索**：老師示範用。分步驟提示、先預測再驗證、關鍵轉換有動畫（例如 10 個一合成 1 條十），具體物、圖示、算式三層同步，可逐層隱藏撤除鷹架。
- **學生練習**：學生直接在介面上用教具解題，再把答案寫進直式的格子。不計時、不計分，答錯時給具體提示並帶回操作，答對時針對過程讚美。做完會出現「老師小結」（預測、是否用教具、提示次數），只顯示在畫面上、不儲存。
- **學習單**：設定題數、題型、是否附位值格與解答頁，預覽後可列印、存成 PDF 或下載學習單檔。

## 老師功能

- 🔈／🔊 **自動報讀**：識字量低的學生建議開啟，題目、提示與回饋都會自動念出。
- 🗣 **語音設定**：風格可直接選瀏覽器提供的中文語音，另有分段慢讀；語速用滑桿調整，會顯示數字（0.5 到 1.5）。選完會自動試聽。可選的語音依電腦或平板而不同。
- ✎ **自己出題**：輸入 IEP 目標或課本上的題目，練習與學習單都用這幾題。
- 🔒 **學生模式**：把平板交給學生前按一下，老師功能全部藏起來；長按右上角「老師」2 秒才能解除。
- 也可以用網址直接設定：`?student=1` 學生模式、`?read=1` 自動報讀、`?q=27+15,38+24` 指定題目。

介面規格：單一 HTML 檔（不需網路）、SVG 繪圖、平板觸控拖曳與點一下放入、按鈕至少 44×44 像素、頂部模式切換、左問題右操作、底部元件選單、撤銷與重置、分數一律直式呈現、色彩編碼（個位藍、十位紅）。

## 安裝（Claude、ChatGPT、Gemini 都可以用）

先點本頁上方綠色的「Code」按鈕，選「Download ZIP」，解壓縮。

| 資料夾／檔案 | 給誰用 |
|---|---|
| `math-concept-visualizer/` | Claude |
| `gpt-gemini/instructions.md` | ChatGPT、Gemini（貼到「指示」） |
| `gpt-gemini/example-template.html` | ChatGPT、Gemini（上傳成「知識」檔案） |

### Claude

1. 把 `math-concept-visualizer` 資料夾（內含 `SKILL.md` 與 `references`）單獨壓縮成 zip。
2. 到 Claude 的「設定 → 功能（Capabilities）→ Skills」上傳這個 zip。
3. 開新對話直接說「請幫我做一個二年級進位加法的教材」，skill 會自動啟用。

Claude Code 使用者可直接把 `math-concept-visualizer` 資料夾放到 `~/.claude/skills/`。

### ChatGPT（建立 GPT）

1. 到 ChatGPT 左側「GPT」→「建立」→ 切到「設定（Configure）」。
2. 名稱：數學概念動態表徵介面小幫手。
3. 「指示（Instructions）」：打開 `gpt-gemini/instructions.md`，全文複製貼上（約 7,000 字，在 8,000 字上限內）。
4. 「知識（Knowledge）」：上傳 `gpt-gemini/example-template.html`。
5. 「功能」：勾選「Canvas」與「程式碼解譯器」。
6. 對話開場白可填：「請幫我做一個二年級二位數進位加法的教材」「我要做數學教材，要怎麼開始？」。
7. 儲存，選「只有知道連結的人」就能分享給其他老師。

### Gemini（建立 Gem）

1. 到 Gemini 左側「Gem 管理員」→「新增 Gem」。
2. 名稱：數學概念動態表徵介面小幫手。
3. 「指示」：打開 `gpt-gemini/instructions.md`，全文複製貼上。
4. 「知識」：上傳 `gpt-gemini/example-template.html`。
5. 預設工具選「Canvas」（若有此選項）。
6. 儲存後可用「共用」分享給其他老師。

不想建 Gem 或 GPT 時，也可以在新對話開頭先貼上 `instructions.md` 全文、附上 `example-template.html`，再提出需求。

### 三種 AI 的差別

- **Claude** 的規則最完整（含自我檢查清單與特教調整表），範例檔已內含，會自動啟用。
- **ChatGPT／Gemini** 用精簡版指示，核心功能相同；一定要上傳範例檔當知識檔案，產出品質才會穩定。
- 不論哪一種，都可以用「保留○○、把○○換成○○」的方式滾動式微調。

## 使用範例

簡單版：

```
請幫我做一個二年級二位數進位加法的教材。
```

完整版：

```
我想針對五年級學習障礙學生設計比率教材，希望透過視覺化表徵呈現全體與部分的關係，並讓學生練習用分數表示，學習單 10 題附解答。
```

微調：

```
保留位值板，把練習改成 10 題，按鈕再放大一點。
```

## 範例教材

`math-concept-visualizer/references/template.html` 是可直接用瀏覽器打開的完整範例（二位數進位加法），也是 skill 製作其他概念時的骨架。

## 注意事項

- 教材是單一 HTML 檔，不需要網路，下載後在電腦、平板或電子白板的瀏覽器都能開。
- 在 Claude、ChatGPT 或 Gemini 的預覽框中，下載按鈕可能被瀏覽器擋住，可改用「列印／存成 PDF」，或先下載整份 HTML 再開啟。
- 本 skill 供成人製作教材使用，教材不要求輸入學生姓名，也不儲存學生作答。
