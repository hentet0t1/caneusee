# 半畝方糖｜帝國製糖廠影展專題網站

行銷系大二影展專題「半畝方糖」的介紹網站。主題是帝國製糖廠臺中營業所，內容依本組企劃書與影展短片整理。

- 作者：紀馨喬（D1483936）
- 課程：Project 1（115-1 行銷系）
- 製作方式：Vibe Coding，用 AI（Claude）依照我的指令產生程式碼，再由我檢查、預覽與修改

## 網站連結

- GitHub：（貼上本 repository 網址）
- InfinityFree：（貼上部署後的網址）
- Vercel：（貼上部署後的網址）

## 我使用的 Vibe Coding 指令

以下是製作這個網站時，我給 AI 的主要指令，依使用順序排列。

### 1. 指定主題與素材

> 我接下來要以 HW07 的規模做另一個不同主題的網頁，文字、照片、影片都要改。這次是我們影展的主題：帝國製糖廠臺中營業所。照片、企劃書都給你，影片連結是（YouTube 嵌入碼）。

AI 讀了企劃書，整理出糖廠的歷史年份、短片故事、目標客群與競爭者比較，寫成網頁內容。

### 2. 依照作業要求檢查

> 我發現老師還有其他要求，你可以幫我確認一下，看有沒有做錯嗎？（附上 Project 1 作業說明截圖）

AI 逐項比對作業要求，找出還沒做到的部分：多頁、側邊欄、Grid、CSS 切割、images 資料夾和 md 檔。

### 3. 改成完整的多頁網站

> 可以先做好。（附上營業所照片檔）

AI 把單頁改成五個分頁，加入共用導覽列與側邊欄，用 CSS Grid 排版，CSS 拆成四個檔案，照片放進 images 資料夾。

### 4. 處理預覽問題

> 下載出來那個 html 顯示不出顏色和格式。

原因是我直接在 zip 壓縮檔裡打開 HTML，css 資料夾沒有一起解壓縮出來。先「解壓縮全部」再打開，就正常了。

## 網站結構

```text
├── index.html        首頁（landing page）：封面大圖、專題介紹、四張分頁卡片
├── story.html        糖廠故事：歷史沿革、場域現況、三個特色
├── film.html         影展短片：故事大綱、YouTube 短片、廣告目標、視覺概念
├── visit.html        走讀地圖：建議路線、場域比較表、Google 地圖、走讀提醒
├── team.html         製作團隊：組員分工、企劃摘要、資料來源
├── README.md         本說明檔
├── css/
│   ├── base.css        基礎樣式：字型、顏色、標題、段落、連結、圖片
│   ├── layout.css      版面：整頁 Grid、頁首、導覽列、主要內容、側邊欄、頁尾
│   ├── components.css  元件：卡片、數字區、時間軸、表格、影片、地圖、個別樣式
│   └── responsive.css  RWD：平板與手機的 @media 規則
└── images/
    └── sugar-factory.jpg  營業所照片（來源：臺中觀光旅遊網）
```

## 作業要求對照

| 要求 | 做法 |
| --- | --- |
| 導覽列、側邊欄、分頁 | 五個分頁共用 `nav` 導覽列，目前頁面用 `aria-current="page"` 標示；每頁右側有 `aside` 側邊欄 |
| SEO | 每頁有自己的 `title`、`description`、`keywords`、Open Graph，並使用 header、nav、main、section、aside、footer 等語意標籤 |
| Grid System | `.page-layout` 用 `grid-template-areas` 切出整頁版面；導覽列、卡片、數字區、側邊欄也都用 Grid |
| RWD | 900px 以下側邊欄移到內容下方；600px 以下導覽列變兩欄、卡片與數字區變一欄、表格可左右捲動 |
| CSS 切割 | 分成 base、layout、components、responsive 四個檔案，都放在 `css` 資料夾 |
| 圖片放 images | 照片放在 `images/sugar-factory.jpg`，HTML 用相對路徑載入 |

## 本機預覽

建議用 VS Code 的 Live Server 打開 `index.html`。直接點兩下開啟 HTML 也能看到樣式，但 YouTube 影片可能因為 `file://` 而出現錯誤 153。

## 資料來源

- 臺中觀光旅遊網：帝國製糖廠臺中營業所（照片來源）
- 本組企劃書「半畝方糖」（引用臺中市文化資產處、臺中市政府經濟發展局資料）
- YouTube：影展短片「半畝方糖」
