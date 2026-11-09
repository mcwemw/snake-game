# 陽明交通大學 資訊科學與工程研究所 414551035 Mei_Chen_WU — A05 用 Vibe Coding 做互動網頁

## 作品：🦞 呆萌演算法視覺化小幫手（路徑搜尋互動圖解）

> 這是我 A03/A04 設計的「呆萌知識小幫手」其中一項功能——**階段性解說＋圖解**——的實體化：把抽象的尋路演算法變成看得到、可操作的動畫。

---

## 一、規格書（和 AI 討論後整理）

### 1. 想解決的問題
學生在學 BFS/DFS/Dijkstra/A* 時，課本只給虛擬碼，很難「看見」演算法為什麼這樣走、誰比較快。我想做一個**在瀏覽器就能玩**的視覺化工具，讓使用者自己畫障礙、按開始，就能看到搜尋過程與最短路徑。

### 2. 目標使用者與情境
- 競賽演算法初學者（APCS/TOI）、想直觀理解搜尋演算法的學生。
- 課餘用手機或電腦打開單一網頁即可操作，不需安裝任何東西。

### 3. 功能規格（Input → Output）

| 輸入（使用者操作） | 輸出（網頁回應） |
|---|---|
| 在格子上**拖曳**畫牆／擦牆 | 格子即時變成牆（深色）或清除 |
| 切「移動起點／終點」後點格子 | 綠色起點／紅色終點移到該格 |
| 選**演算法**（BFS/DFS/Dijkstra/A*） | 決定搜尋策略 |
| 拉**速度**滑桿 | 動畫快慢（每步延遲） |
| 按**開始尋路** | 動畫逐格顯示：待探索(frontier)→已探索(藍)→最短路徑(金) |
| 按**隨機迷宮** | 隨機生成約 28% 密度的牆 |
| 按**清除路徑／全部重設** | 清掉搜尋結果／回到初始盤面 |
| 即時統計 | 探索節點數、路徑長度（步數）、耗時(ms)、狀態 |

### 4. 成功標準
- 四種演算法都能正確找到路（或正確回報「無路可達」），且 **A* 探索的節點明顯少於 BFS**（可切換對照）。
- 全程在**單一 `index.html`**（HTML+CSS+JS 內嵌），開啟即用、手機可操作。

### 5. 技術規格
- 純前端，無任何外部函式庫或 CDN，單檔 `index.html`。
- 演算法：BFS（queue）、DFS（stack）、Dijkstra（等權 PQ）、A*（Dijkstra + 曼哈頓距離啟發式）。
- 動畫用 `async/await + setTimeout` 逐步上色；觸控與滑鼠事件統一處理（手機可畫牆）。
- 配色沿用我的 ACROBUSTER 品牌色票（navy/green/red/gold）。

### 6. 與 AI 反覆調整的紀錄（Vibe Coding 過程）
1. 先請 AI 產出基本 BFS grid 版本 → 問題：只有 BFS、無法對照。
2. 加入 DFS/Dijkstra/A*，統一成「記錄 steps 再動畫重播」的架構 → 解決動畫與邏輯耦合。
3. 手機拖曳畫牆失效 → 改用 `elementFromPoint` + `touchmove preventDefault` 修好。
4. 補 frontier/visited/path 三色圖例、即時統計、隨機迷宮、速度滑桿，讓它「真的能玩」而非靜態展示。

---

## 二、網站連結
- GitHub Pages：**https://mcwemw.github.io/snake-game/A05-vibe-web/** （需先在 repo Settings→Pages 開啟 main 分支）
- 原始碼：`index.html`（同一 repo）

## 三、介面截圖
- `screenshot-initial.png`：初始盤面（起點/終點/控制列）
- `screenshot-run.png`：A* 搜尋後（藍=已探索 131 格、金=最短路 30 步）

---

### 部署（GitHub Pages）
1. 把 `index.html` 放到 GitHub repo。
2. repo → Settings → Pages → Source 選 `main` 分支（或 `/docs`）→ Save。
3. 幾分鐘後得到公開網址 `https://<帳號>.github.io/<repo>/.../index.html`。
