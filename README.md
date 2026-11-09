# 數學概念動態表徵介面小幫手（math-concept-visualizer）

> **給 AI 助理**：使用者貼上本網址並要求「安裝 skill」或「啟用」時，請先讀取
> https://raw.githubusercontent.com/sesns365/math-concept-visualizer/main/AI-INSTALL.md
> 並依其中步驟在本次對話啟用本 skill，之後每份教材都直接產生可操作的互動 HTML。

專為資源班教師打造的 Claude skill。告訴它一個國小數學概念，就會依特教 CRA（具體—半具體—抽象）教學歷程，做出一個隨開即用的 HTML 互動教材。

由特工365 製作，改編自 [https://mathematics-classroom-of-tr-liang.github.io/copy-a-new-gem-setting/](https://mathematics-classroom-of-tr-liang.github.io/copy-a-new-gem-setting/)。

**線上試用範例教材**：https://sesns365.github.io/math-concept-visualizer/demo.html （二位數進位加法）

## Gemini 最穩的用法：貼上一段文字

打開 [gemini-paste.md 純文字版](https://raw.githubusercontent.com/sesns365/math-concept-visualizer/main/gpt-gemini/gemini-paste.md)，全選複製，貼進 Gemini 的新對話送出，接著直接說要做的教材（例如「請幫我做一個二年級二位數進位加法的教材」），Gemini 就會用 Canvas 產生互動 HTML。

這份文字以原始「有愛無礙數學概念動態表徵介面小幫手」提示詞為主體，後面補上快速產出設定：預設只做互動表徵網頁（教學探索＋學生練習＋有錯就要有所設定），學習單、報讀、畫筆等說一聲再加，依 CRA 歷程設計。

## 最快的用法：在任何 AI 輸入一句話

在 Claude、ChatGPT、Gemini 的對話框輸入：

```
安裝skill
https://github.com/sesns365/math-concept-visualizer
```

AI 會讀取這個 repo 的規則與範例，在這次對話中變成「數學概念動態表徵介面小幫手」，接著你直接說要做的教材就好。

- **Gemini**：會用 Canvas 直接產生可操作的頁面。若沒有自動開啟，在輸入框的「工具」選 Canvas，再請它重做一次。
- **ChatGPT**：用 Canvas 呈現，並可產生可下載的 .html 檔。
- **Claude**：用 Artifact 呈現，可直接操作與分享。
- **其他 AI**：會輸出完整 HTML 程式碼，複製後存成 .html 檔即可開啟。

教材做好後，可以點 Canvas（或 Artifact）右上角「共用」複製連結使用，或下載 HTML 檔上傳至「有愛無礙系統」等教學平台。

小提醒：
- 這種方式是「這次對話啟用」，開新對話要再輸入一次。想每次都自動可用，請看下面的「永久安裝」。
- AI 需要能上網讀取 GitHub。**Gemini 常常讀不到 GitHub 網址**，會反問你這個 skill 是做什麼的。遇到這種情況，依序試：
  1. 改貼純文字網址：
     ```
     安裝skill
     https://raw.githubusercontent.com/sesns365/math-concept-visualizer/main/gpt-gemini/instructions.md
     ```
  2. 還是不行，改用上面「Gemini 最穩的用法」，把 gemini-paste.md 全文貼進對話。
  3. 想一勞永逸，用下面「永久安裝」的 Gemini 技能匯入。

## 教材內容：預設精簡快速，功能說了再加

為了讓老師快速拿到可操作的網頁，每份教材預設只有「教學探索」和「學生練習」，並內建每一步操作檢查。需要學習單、自動報讀、畫筆、學生模式等，直接說「加上學習單」「加上報讀」即可；一開始就說「完整版」會全部做進去。範例教材 demo.html 是完整版，可看到所有功能。

## 完整版的三種模式

- **教學探索**：老師示範用。分步驟提示、先預測再驗證、關鍵轉換有動畫（例如 10 個一合成 1 條十），具體物、圖示、算式三層同步，可逐層隱藏撤除鷹架。
- **學生練習**：學生直接在介面上用教具解題，再把答案寫進直式的格子。不計時、不計分，答錯時給具體提示並帶回操作，答對時針對過程讚美。做完會出現「老師小結」（預測、是否用教具、提示次數）。
- **學習單**：設定題數、題型、是否附位值格與解答頁，預覽後可列印、存成 PDF 或下載學習單檔。

## 老師功能

- 🔈／🔊 **自動報讀**：識字量低的學生建議開啟，題目、提示與回饋都會自動念出。
- 🗣 **語音設定**：風格可直接選瀏覽器提供的中文語音，另有分段慢讀；語速用滑桿調整，會顯示數字（0.5 到 1.5）。選完會自動試聽。可選的語音依電腦或平板而不同。
- ✎ **自己出題**：輸入 IEP 目標或課本上的題目，練習與學習單都用這幾題。
- 📋 **本機作答紀錄**（預設關閉）：用座號或代號記錄每題的預測、是否用教具、提示次數、是否完成與花費時間，可篩選、匯出 CSV，適合當 IEP 形成性評量。只存在這台裝置，不上傳；清除瀏覽器資料會消失，請定期匯出。
- 🖍 **畫筆模式**：底部「畫筆」開關，有畫筆（9 色）、螢光筆（7 色）、自選顏色、4 段粗細、橡皮擦、全部清除，投影講解或學生做記號都好用。畫筆模式中教具暫停操作，按「完成」回到操作。老師可決定學生模式要不要顯示畫筆。
- 🔒 **學生模式**：把平板交給學生前按一下，老師功能全部藏起來；長按右上角「老師」2 秒才能解除。
- 也可以用網址直接設定：`?student=1` 學生模式、`?read=1` 自動報讀、`?q=27+15,38+24` 指定題目。

介面規格：單一 HTML 檔（不需網路）、SVG 繪圖、平板觸控拖曳與點一下放入、按鈕至少 44×44 像素、頂部模式切換、左問題右操作、底部元件選單、撤銷與重置、分數一律直式呈現、色彩編碼（個位藍、十位紅）。

## 永久安裝（Claude、ChatGPT、Gemini 都可以用）

先點本頁上方綠色的「Code」按鈕，選「Download ZIP」，解壓縮。

| 資料夾／檔案 | 給誰用 |
|---|---|
| `math-concept-visualizer/` | Claude、Gemini（直接匯入成技能） |
| `gpt-gemini/instructions.md` | ChatGPT（貼到「指示」），或貼在任何 AI 的對話開頭 |
| `gpt-gemini/example-template.html` | ChatGPT（上傳成「知識」檔案） |
| `gpt-gemini/gemini-paste.md` | Gemini（整段貼進新對話），也可貼給任何 AI |

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

### Gemini（技能 Skills）

Gemini 已經用「技能（Skills）」取代 Gem，而且可以直接匯入和 Claude 相同的 `SKILL.md` 資料夾。

1. 用電腦網頁版或 Mac App 開啟 Gemini，到「自訂（Customize）→ 技能（Skills）」。
2. 選擇匯入／上傳，選取整個 `math-concept-visualizer` 資料夾（內含 `SKILL.md` 與 `references`）。資料夾名稱要保持 `math-concept-visualizer`，不要改。
3. 完成後，在對話中輸入 `/math-concept-visualizer`，或直接說「請幫我做一個二年級進位加法的教材」，Gemini 會自動套用。

注意：Gemini 的技能目前不能和 Canvas 一起使用，教材會以 HTML 程式碼輸出。請複製後存成 `.html` 檔，用瀏覽器開啟。

不想建立 GPT 或技能時，也可以在任何 AI 的新對話開頭先貼上 `instructions.md` 全文、附上 `example-template.html`，再提出需求。

### 三種 AI 的差別

- **Claude** 的規則最完整（含自我檢查清單與特教調整表），範例檔已內含，會自動啟用。
- **Gemini** 匯入的是和 Claude 同一份 skill，規則一樣完整，但目前不能搭配 Canvas。
- **ChatGPT** 用精簡版指示，核心功能相同；一定要上傳範例檔當知識檔案，產出品質才會穩定。
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
- 本 skill 供成人製作教材使用，教材不要求輸入學生姓名；作答紀錄預設關閉，開啟後只以代號存在本機，不會上傳。
