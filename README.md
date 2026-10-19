貪食蛇 (Snake) – Vibe Coding 作業
專案說明
這是一個使用純 HTML、CSS 與 JavaScript 實作的 貪食蛇 小遊戲，透過 Vibe Coding（AI協助）從概念討論、規格書撰寫到程式實作、除錯以及發布於 GitHub Pages 的完整流程。

遊戲玩法
使用 ↑ ↓ ← → 鍵盤方向鍵控制蛇的移動方向。
蛇吃到隨機出現的紅色食物後，身體會變長一格且得分 +1。
若蛇頭撞到牆壁或自己的身體，遊戲結束，顯示「Game Over」並提供「重新開始」按鈕。
介面上方提供 速度選單（慢 / 中 / fast），可即時調整遊戲進行速度。
點擊「開始遊戲」或「重新開始」即可開始新的一局。
本地測試方式
將此儲存庫（repository）克隆或下載 ZIP 至本機。
找到 index.html 檔案，直接使用瀏覽器（Chrome、Firefox、Safari 等）開啟該檔案。
無需安裝任何額外的依賴套件或伺服器，純前端即可遊玩。
檔案結構


snake-game/
├─ index.html   # 主遊戲頁面（含 HTML、CSS、JavaScript）
└─ README.md    # 此說明檔
技術要點
HTML：結構化遊戲介面（分數顯示、速度選單、開始按鈕、遊戲棋盤）。
CSS：使用 Grid 佈局建立 20×20 的棋盤，並自訂蛇身、蛇頭與食物的顏色。
JavaScript：
資料結構：snake（陣列）、food（座標物件）、direction、score、tickInterval。
遊戲迴圈：setInterval 依據選擇的速度更新狀態。
碰撞檢測：牆壁與身體自碰撞。
鍵盤事件：方向鍵控制，並防止 180° 直接反轉。
速度選單：即時更改 tickInterval 以改變難度。
未來可能的擴充功能（可作為後續練習）
暫停 / 繼續功能（Space 鍵或按鈕）。
最高分紀錄（使用 localStorage）。
觸控版方向按鈕（適合行動裝置）。
不同地圖大小或障礙物設計。
音效與背景音樂（使用 Web Audio API 或 HTML5 <audio>）。
參與與回饋
若您有任何改進建議或發現 Bug，歡迎提出 Issue 或直接提交 Pull Request。感謝使用與學習！

此專案為第五週作業 1006 「用 Vibe Coding 做出一個互動網頁」的實作成果。
製作者：吳美真（NYCU 資訊科學工程研究所）
製作日期：2026 年 10 月
