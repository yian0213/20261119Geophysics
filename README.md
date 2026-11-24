# 爆炸地震學（Forensic Seismology）講座筆記網頁

本專案將中研院地球科學研究所 **梁文宗 老師** 於臺北市立大學主講之**「爆炸地震學：從觀測角度看非天然地震」** 完整講座紀錄（含 7.4 萬字音頻校勘逐字稿、現場 Q&A 與學生專題實錄）轉換為具有**地球物理／地震觀測站風格**的響應式網頁，可直接部署於 **GitHub Pages**。

---

## 🌐 網頁特點

1. **地震監測站 UI 風格**：
   - 採用深色構造板塊灰藍（Tectonic Slate）與地震波形網格背景。
   - 地震規模專屬色彩標籤（$M \ge 6.0$ 烈紅、$M \ge 5.0$ 橙黃等）。
   - 震波波相晶片標籤（`Pg`、`Pn`、`Lg`、`Multiple`）。
2. **動態地震儀波形模擬（Live Seismograph Canvas）**：
   - 頂部即時繪製三分量（Z、R、T）震波走時背景雜訊。
   - 提供「觸發模擬人工炸測」按鈕，動態展示 P 波初達、橫波/導波 Lg 與 Coda 衰減。
3. **互動式 20 秒地殼共振計算器**：
   - 即時調整 S 波速度與週期，重現大陸地殼 35 km 半波長共振推導。
4. **YouTube 影音精準時間戳記連動**：
   - 內建 56 處 `[hh:mm:ss]` 時間戳記，點擊即可展開置頂同步播放器並直接跳轉至該秒數。
5. **完整保留 900+ 行深入紀錄**：
   - 涵蓋法醫地震學 6 大實例、北韓核試爆 5 項辨識指標、台灣 TIGER 炸測晶圓廠停機事件、沖積層衰減異常、學生 4 大類振動專題（含大巨蛋演唱會共振）與老師的方法論回饋（STA/LTA、Bootstrap）。

---

## 🚀 如何上傳到 GitHub 並開啟網頁（GitHub Pages）

### 步驟 1：建立 GitHub Repository
1. 登入 [GitHub](https://github.com/)，點選右上角 **New repository**。
2. 輸入儲存庫名稱（例如 `forensic-seismology` 或 `earthquake-notes`）。
3. 設為 **Public**，點擊 **Create repository**。

### 步驟 2：上傳檔案
在本地資料夾開啟終端機（PowerShell / Git Bash），執行以下指令：

```bash
git init
git add .
git commit -m "feat: initial commit for forensic seismology web"
git branch -M main
git remote add origin https://github.com/<你的GitHub帳號>/<你的儲存庫名稱>.git
git push -u origin main
```

*(如果不會用 Git 指令，也可以直接在 GitHub 網頁上點選 **Add file -> Upload files**，把 `index.html` 與相關檔案拖拉上傳並 commit)*

### 步驟 3：開啟 GitHub Pages
1. 在 GitHub 該專案頁面點選上方 **Settings**。
2. 在左側選單點選 **Pages**。
3. 在 **Build and deployment** 下方的 **Branch**：
   - 選擇 `main`
   - 資料夾選擇 `/(root)`
   - 點擊 **Save**。
4. 等候約 1~2 分鐘，重整頁面即可看到網址：
   `https://<你的GitHub帳號>.github.io/<你的儲存庫名稱>/`

---

## 📁 檔案結構說明

- `index.html`：**主要網頁檔案**（單一靜態 HTML，GitHub Pages 預設首頁，包含完整 CSS、JS、Canvas 與 SVG 圖解，可直接開啟）
- `01_地震講座_梁文宗_爆炸地震學_紀錄與心得.md`：原始完整 Markdown 筆記（906行）
- `build.py`：Python 轉換腳本（若日後有修改 markdown，執行 `python build.py` 即可自動重新生成 `index.html`）
- `README.md`：本專案說明與部署指引
