<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>超可愛自定義迷因產生器 🐾</title>
    <!-- 引入 Google Fonts：可愛風圓體字型 -->
    <link href="https://fonts.googleapis.com/css2?family=ZCOOL+KuaiLe&family=Noto+Sans+TC:wght@500;700&display=swap" rel="stylesheet">
    <!-- 引入 html2canvas CDN 用於截圖下載 -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    
    <style>
        /* CSS 樣式設定：全站可愛風格與 RWD 響應式排版 */
        :root {
            --primary-color: #ff85a2; /* 粉紅色 */
            --secondary-color: #ffb7b2; /* 淺粉色 */
            --bg-color: #fff0f3; /* 柔和背景粉 */
            --card-bg: #ffffff;
            --text-color: #555555;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Noto Sans TC', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            align-items: center;
            padding: 20px;
        }

        header {
            margin-bottom: 20px;
            text-align: center;
        }

        header h1 {
            font-family: 'ZCOOL KuaiLe', cursive;
            color: var(--primary-color);
            font-size: 2.5rem;
            text-shadow: 2px 2px 0px #ffe5ec;
        }

        header p {
            font-size: 0.95rem;
            color: #888;
        }

        /* 主容器：採用 Flexbox 左右分割，手機版會自動變成上下堆疊 */
        .main-container {
            display: flex;
            gap: 24px;
            width: 100%;
            max-width: 1000px;
            background: var(--card-bg);
            padding: 24px;
            border-radius: 24px;
            box-shadow: 0 10px 25px rgba(255, 133, 162, 0.15);
        }

        /* 左側：控制面板區 */
        .control-panel {
            flex: 1;
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .control-group {
            display: flex;
            flex-direction: column;
            gap: 6px;
        }

        .control-group label {
            font-weight: 700;
            font-size: 0.9rem;
            color: #666;
        }

        /* 自定義美化檔案上傳按鈕 */
        .file-upload-btn {
            background-color: var(--secondary-color);
            color: white;
            padding: 12px;
            border-radius: 12px;
            text-align: center;
            cursor: pointer;
            font-weight: bold;
            transition: 0.2s;
        }

        .file-upload-btn:hover {
            background-color: var(--primary-color);
        }

        input[type="file"] {
            display: none; /* 隱藏原生 ugly 的檔案上傳框 */
        }

        input[type="text"] {
            padding: 10px 14px;
            border: 2px solid #ffd1dc;
            border-radius: 12px;
            font-size: 1rem;
            outline: none;
            transition: 0.2s;
            font-family: 'Noto Sans TC', sans-serif;
        }

        input[type="text"]:focus {
            border-color: var(--primary-color);
        }

        /* 滑桿美化 */
        input[type="range"] {
            accent-color: var(--primary-color);
            cursor: pointer;
        }

        /* 下載按鈕 */
        .download-btn {
            background: linear-gradient(135deg, #ff85a2, #ffb7b2);
            color: white;
            border: none;
            padding: 14px;
            border-radius: 14px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 4px 12px rgba(255, 133, 162, 0.3);
            transition: transform 0.1s, box-shadow 0.1s;
            margin-top: 10px;
            text-align: center;
        }

        .download-btn:active {
            transform: scale(0.98);
        }

        /* 右側：迷因即時預覽區 */
        .preview-panel {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #faf0f2;
            border-radius: 16px;
            padding: 16px;
            border: 2px dashed #ffccd5;
            overflow: hidden;
        }

        /* 迷因畫布區（要被截圖下載的區塊） */
        #meme-card {
            position: relative;
            width: 100%;
            max-width: 400px;
            aspect-ratio: 1 / 1; /* 保持正方形比例 */
            background-color: #ddd;
            border-radius: 12px;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        #meme-card img {
            width: 100%;
            height: 100%;
            object-fit: cover; /* 讓圖片填滿不變形 */
        }

        /* 預設提示文字（當沒有上傳圖片時顯示） */
        .placeholder-text {
            position: absolute;
            color: #aaa;
            font-weight: bold;
            pointer-events: none;
        }

        /* 迷因雙層文字通用樣式 (使用強力 text-shadow 確保任何背景都看得見) */
        .meme-text {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            text-align: center;
            font-family: 'ZCOOL KuaiLe', cursive;
            color: #ffffff;
            text-shadow: 
                -2px -2px 0 #000,  
                 2px -2px 0 #000,
                -2px  2px 0 #000,
                 2px  2px 0 #000,
                 0px 3px 6px rgba(0,0,0,0.6);
            word-break: break-all;
            pointer-events: none; /* 避免文字擋住滑鼠操作 */
            line-height: 1.2;
        }

        #top-text-output {
            top: 5%; /* 預設位置，會由 JS 隨滑桿動態調整 */
        }

        #bottom-text-output {
            bottom: 5%; /* 預設位置，會由 JS 隨滑桿動態調整 */
        }

        /* RWD 響應式設計：當螢幕小於 768px (手機版) 時改為上下排列 */
        @media (max-width: 768px) {
            .main-container {
                flex-direction: column;
                padding: 16px;
            }
            header h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>🐾 超可愛迷因產生器 🐾</h1>
        <p>上傳照片、輸入文字，輕鬆製作獨一無二的萌系迷因！</p>
    </header>

    <div class="main-container">
        <!-- 左側：控制面板 -->
        <div class="control-panel">
            <!-- 1. 圖片上傳 (使用 input type="file" 避開 CORS 錯誤) -->
            <div class="control-group">
                <label>1. 選擇底圖照片</label>
                <label for="image-upload" class="file-upload-btn">📁 點此上傳電腦中的圖片</label>
                <input type="file" id="image-upload" accept="image/*">
            </div>

            <!-- 2. 上方文字輸入 -->
            <div class="control-group">
                <label for="top-text-input">2. 上方文字</label>
                <input type="text" id="top-text-input" placeholder="請輸入上方文字...">
            </div>

            <!-- 3. 下方文字輸入 -->
            <div class="control-group">
                <label for="bottom-text-input">3. 下方文字</label>
                <input type="text" id="bottom-text-input" placeholder="請輸入下方文字...">
            </div>

            <!-- 4. 字體大小滑桿 -->
            <div class="control-group">
                <label for="font-size-range">字體大小調整: <span id="font-size-val">32</span>px</label>
                <input type="range" id="font-size-range" min="16" max="64" value="32">
            </div>

            <!-- 5. 上方文字垂直位置滑桿 -->
            <div class="control-group">
                <label for="top-pos-range">上方文字垂直位置: <span id="top-pos-val">5</span>%</label>
                <input type="range" id="top-pos-range" min="2" max="45" value="5">
            </div>

            <!-- 6. 下方文字垂直位置滑桿 -->
            <div class="control-group">
                <label for="bottom-pos-range">下方文字垂直位置: <span id="bottom-pos-val">5</span>%</label>
                <input type="range" id="bottom-pos-range" min="2" max="45" value="5">
            </div>

            <!-- 7. 一鍵截圖下載按鈕 -->
            <button class="download-btn" id="download-btn">✨ 下載我的可愛迷因 ✨</button>
        </div>

        <!-- 右側：即時預覽區 -->
        <div class="preview-panel">
            <!-- 準備被 html2canvas 截圖的卡片容器 -->
            <div id="meme-card">
                <div class="placeholder-text" id="placeholder">尚未選擇圖片呦 ~</div>
                <img id="image-preview" src="" alt="" style="display: none;">
                <div class="meme-text" id="top-text-output"></div>
                <div class="meme-text" id="bottom-text-output"></div>
            </div>
        </div>
    </div>

    <script>
        // 取得 DOM 元素
        const imageUpload = document.getElementById('image-upload');
        const imagePreview = document.getElementById('image-preview');
        const placeholder = document.getElementById('placeholder');
        
        const topTextInput = document.getElementById('top-text-input');
        const bottomTextInput = document.getElementById('bottom-text-input');
        
        const topTextOutput = document.getElementById('top-text-output');
        const bottomTextOutput = document.getElementById('bottom-text-output');
        
        const fontSizeRange = document.getElementById('font-size-range');
        const fontSizeVal = document.getElementById('font-size-val');
        
        const topPosRange = document.getElementById('top-pos-range');
        const topPosVal = document.getElementById('top-pos-val');
        
        const bottomPosRange = document.getElementById('bottom-pos-range');
        const bottomPosVal = document.getElementById('bottom-pos-val');
        
        const downloadBtn = document.getElementById('download-btn');

        // 功能 1：處理本機圖片上傳與 FileReader 預覽
        imageUpload.addEventListener('change', function(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    imagePreview.src = e.target.result;
                    imagePreview.style.display = 'block';
                    placeholder.style.display = 'none'; // 隱藏提示文字
                }
                reader.readAsDataURL(file); // 讀取圖片轉成 Base64 格式
            }
        });

        // 功能 2：即時雙層文字同步更新
        topTextInput.addEventListener('input', function() {
            topTextOutput.textContent = this.value;
        });

        bottomTextInput.addEventListener('input', function() {
            bottomTextOutput.textContent = this.value;
        });

        // 功能 3：字體大小滑桿連動
        fontSizeRange.addEventListener('input', function() {
            const size = this.value;
            fontSizeVal.textContent = size;
            topTextOutput.style.fontSize = size + 'px';
            bottomTextOutput.style.fontSize = size + 'px';
        });

        // 功能 4：上方文字垂直位置調整 (Top%)
        topPosRange.addEventListener('input', function() {
            const pos = this.value;
            topPosVal.textContent = pos;
            topTextOutput.style.top = pos + '%';
            topTextOutput.style.bottom = 'auto'; // 解除底部限制
        });

        // 功能 5：下方文字垂直位置調整 (Bottom%)
        bottomPosRange.addEventListener('input', function() {
            const pos = this.value;
            bottomPosVal.textContent = pos;
            bottomTextOutput.style.bottom = pos + '%';
            bottomTextOutput.style.top = 'auto'; // 解除頂部限制
        });

        // 功能 6：使用 html2canvas 實作一鍵截圖下載
        downloadBtn.addEventListener('click', function() {
            // 檢查是否有上傳圖片
            if (imagePreview.style.display === 'none') {
                alert('請先上傳一張可愛的底圖再下載喔！🐾');
                return;
            }

            // 呼叫 html2canvas 對 #meme-card 區塊進行截圖
            html2canvas(document.getElementById('meme-card'), {
                useCORS: true, // 允許跨域（本機 FileReader 不會受影響，但保留好習慣）
                scale: 2       // 提高解析度，讓下載的圖片更清晰
            }).then(canvas => {
                // 將 canvas 轉為圖片下載連結
                const link = document.createElement('a');
                link.download = 'my-meme.png'; // 產生的檔案名稱
                link.href = canvas.toDataURL('image/png');
                link.click(); // 模擬點擊下載
            }).catch(err => {
                console.error('截圖失敗：', err);
                alert('下載失敗，請稍後再試！');
            });
        });
    </script>
</body>
</html>
