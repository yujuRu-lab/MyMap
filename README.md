# MyMap
#v1.0-2026/08/18

##1. 程式簡介
**台灣玩透透｜互動旅遊地圖」**是一款以台灣旅遊為主題的互動式網頁應用程式，結合 Leaflet 地圖、Tailwind CSS 與 Vanilla JavaScript，將景點資訊、地圖探索與行程規劃整合在單一介面中。
使用者可以透過地區、主題分類與關鍵字搜尋快速尋找景點，並在地圖上查看景點位置與詳細資訊；同時提供收藏景點、自訂行程、路線距離計算、隨機推薦、新增私人景點、目前位置定位及地圖圖層切換等功能。使用 LocalStorage 儲存使用者的收藏、行程與自訂景點，讓資料在重新整理網頁後仍能保留。
整體設計採用響應式網頁介面，支援桌機與手機操作，打造兼具「景點探索、地圖導航與旅遊行程規劃」的台灣旅遊小工具。

##2. 主要功能
台灣景點互動地圖：以地圖方式呈現全台 21 個熱門景點，並依景點類型使用不同顏色與圖示標記。
多條件景點篩選：可依「北部、中部、南部、東部、離島」及「自然景觀、人文古蹟、夜市美食、親子休閒、拍照打卡」進行篩選。
關鍵字搜尋：可搜尋景點名稱、縣市、景點介紹及標籤。
景點詳細資訊：顯示景點圖片、評分、評論數、介紹、地址、推薦季節與特色標籤。
收藏功能：使用者可以收藏或取消收藏喜愛的景點，並可切換「只顯示收藏」。
自訂旅遊行程：可將景點加入行程，調整景點順序並查看預估總距離。
路線視覺化：利用地圖上的折線呈現景點之間的行程路線。
隨機推薦景點：透過「今天去哪玩？」隨機推薦景點。
新增自訂景點：使用者可以自行建立私人景點，包含名稱、分類、座標、圖片、地址及標籤。
地圖座標選取：可直接在地圖上點擊位置，自動取得景點經緯度。
地圖圖層切換：提供標準街道圖、衛星影像及暗色地圖。
目前位置定位：透過瀏覽器定位功能取得使用者目前位置。
Google Maps 導航：景點詳細頁提供導航連結，可直接開啟 Google Maps。
行程文字複製：可將自訂行程與預估距離複製到剪貼簿。
響應式設計：支援桌機、平板及手機操作。

##3. API／第三方函式庫運用
🗺️ Leaflet.js:　使用 Leaflet 1.9.4 建立互動式地圖，是本作品最主要的第三方 JavaScript 函式庫。
主要應用：
建立台灣互動地圖,建立景點 Marker,自訂景點 Marker 圖示,顯示 Popup 景點資訊,地圖縮放與移動,繪製旅遊路線 Polyline,點擊地圖取得經緯度,地圖圖層切換

🗺️ OpenStreetMap: 作為標準街道地圖的圖資來源：
https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png
提供一般道路與地理位置資訊。

🛰️ Esri World Imagery
使用 ArcGIS/Esri World Imagery 提供衛星影像圖層，讓使用者可以切換衛星地圖。

🌙 CARTO
使用 CARTO Dark Map 建立暗色地圖模式，提供不同的地圖視覺體驗。

🧭 Browser Geolocation API
使用瀏覽器內建的 navigator.geolocation：

navigator.geolocation.getCurrentPosition()
取得使用者目前的：
緯度 Latitude
經度 Longitude
並將地圖移動到使用者目前位置。

📍 Google Maps URL API
透過 Google Maps 的 URL 參數建立導航連結，將景點經緯度帶入導航目的地。

💾 LocalStorage API
使用瀏覽器的 localStorage 儲存：

收藏景點
自訂旅遊行程
使用者新增景點
因此即使重新整理網頁，使用者資料仍可保留。

📋 Clipboard／剪貼簿功能
利用瀏覽器剪貼簿相關功能，將自訂行程轉換成文字並複製，方便分享或保存。

##4. 使用到的技術
技術	應用
HTML5	建立網頁結構與表單元件
CSS3	網頁樣式、動畫、響應式效果
Tailwind CSS	快速建立現代化 UI 與 RWD 介面
Vanilla JavaScript	景點資料、搜尋、篩選、收藏、行程等核心邏輯
Leaflet.js	互動地圖與地圖標記
OpenStreetMap	標準地圖圖資
Esri World Imagery	衛星影像圖資
CARTO	暗色地圖圖資
Font Awesome	地圖、收藏、導航等 UI Icon
Google Fonts / Noto Sans TC	中文網頁字型
LocalStorage	使用者資料持久化儲存
Geolocation API	使用者目前位置定位
Google Maps URL	景點導航
Haversine Formula	計算景點之間的地理距離
Responsive Web Design	支援桌機、平板、手機
