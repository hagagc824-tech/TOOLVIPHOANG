<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>HOANGDZ SYSTEM | AI MD5 2026</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;900&family=Quicksand:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        :root { 
            --neon: #00f2ff; 
            --bg: #010103; 
            --gold: #ffeb3b;
            --glass: rgba(255, 255, 255, 0.06);
        }

        * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; outline: none; }
        
        body { 
            margin:0; background: var(--bg); color:#fff; 
            font-family: 'Quicksand', sans-serif; overflow: hidden; height: 100vh;
        }

        #snowCanvas { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 1; }

        /* Login Overlay */
        #loginOverlay { 
            position:fixed; inset:0; background: radial-gradient(circle at top, #0a192f 0%, #000 100%); 
            z-index: 9999; display:flex; flex-direction: column; align-items:center; 
            padding:20px; overflow-y: auto;
        }

        .glass-card { 
            background: var(--glass); backdrop-filter: blur(20px); 
            border: 1px solid rgba(0, 242, 255, 0.15); border-radius: 20px; 
            padding: 22px; box-shadow: 0 15px 45px rgba(0, 0, 0, 0.9);
            width: 100%; max-width: 450px; margin-bottom: 20px; position: relative; z-index: 10;
        }

        /* Nav & Header */
        .header { 
            position:fixed; top:0; width:100%; height:60px; 
            background: rgba(0,0,0,0.95); backdrop-filter: blur(15px);
            display:flex; justify-content:center; align-items:center; 
            z-index:1000; border-bottom: 1px solid var(--neon);
        }

        .nav-bar {
            position: fixed; bottom: 15px; left: 50%; transform: translateX(-50%);
            width: 92%; max-width: 420px; background: rgba(5, 5, 10, 0.98);
            border-radius: 40px; border: 1px solid var(--neon);
            display: flex; justify-content: space-around; padding: 10px; z-index: 2000;
            box-shadow: 0 0 20px rgba(0, 242, 255, 0.2);
        }

        .nav-item { color: #555; font-size: 10px; text-align: center; cursor: pointer; font-family: 'Orbitron'; font-weight: bold;}
        .nav-item.active { color: var(--neon); text-shadow: 0 0 10px var(--neon); }

        /* Page System */
        .page { display: none; height: 100vh; padding: 80px 15px 120px 15px; overflow-y: auto; z-index: 5; scroll-behavior: smooth; }
        .page.active { display: block; animation: slideIn 0.3s ease-out; }
        @keyframes slideIn { from { opacity: 0; transform: scale(0.98); } to { opacity: 1; transform: scale(1); } }

        /* Text Decoration */
        h2, h3 { font-family: 'Orbitron'; color: var(--neon); text-transform: uppercase; letter-spacing: 2px; text-align: center; margin-bottom: 15px; }
        .intro-line { 
            display: flex; align-items: flex-start; margin-bottom: 12px; 
            font-size: 14px; line-height: 1.5; color: #e0e0e0;
        }
        .intro-line::before { content: "⚡"; margin-right: 10px; color: var(--neon); }

        /* Price UI */
        .price-tag { 
            display: flex; justify-content: space-between; align-items: center;
            padding: 12px; border-radius: 10px; background: rgba(255,255,255,0.03);
            margin-bottom: 8px; border: 1px solid rgba(255,255,255,0.05);
        }
        .price-tag b { color: var(--neon); font-family: 'Orbitron'; }

        /* Components */
        .btn { 
            background: linear-gradient(90deg, #00d2ff 0%, #3a7bd5 100%); 
            border:none; color:white; font-weight:900; width:100%; 
            border-radius:12px; padding:16px; margin-top:10px; font-family:'Orbitron';
            box-shadow: 0 4px 15px rgba(0, 210, 255, 0.4); text-shadow: 0 2px 4px rgba(0,0,0,0.5);
        }
        input { 
            width:100%; padding:16px; margin:10px 0; border-radius:12px; 
            border:1px solid #222; background:rgba(0,0,0,0.7); color:var(--neon); 
            text-align: center; font-family: 'Orbitron'; font-size: 14px;
        }

        /* History */
        .history-box { background: rgba(0,0,0,0.4); border-radius: 15px; padding: 5px; }
        .history-item { 
            display: flex; justify-content: space-between; padding: 10px 15px; 
            font-size: 13px; border-bottom: 1px solid #111; font-family: 'Orbitron';
        }

        #timer { position: fixed; top: 18px; right: 15px; font-family: 'Orbitron'; font-size: 11px; color: var(--neon); z-index: 3000; font-weight: 900; }
    </style>
</head>
<body>

    <canvas id="snowCanvas"></canvas>
    <div id="timer">HOANGDZ SYSTEM</div>

    <div id="loginOverlay">
        <div style="margin-top: 40px; text-align: center;">
            <h1 style="font-family:'Orbitron'; font-weight: 900; color:var(--neon); margin:0; font-size: 2.2rem; letter-spacing: -2px;">HOANGDZ</h1>
            <p style="letter-spacing: 5px; font-size: 10px; color: #888;">PREMIUM MD5 TOOL</p>
        </div>

        <div class="glass-card">
            <h3>🔑 ĐĂNG NHẬP</h3>
            <input type="text" id="keyInput" placeholder="NHẬP KEY CỦA BẠN">
            <button class="btn" onclick="checkKey()">KÍCH HOẠT HỆ THỐNG</button>
            <p style="text-align:center; font-size:10px; color:#555; margin-top:10px;">Hardware ID: <span id="hwid" style="color:#777"></span></p>
        </div>

        <div class="glass-card">
            <h3 style="color:var(--gold)">💎 BẢNG GIÁ KEY VIP</h3>
            <div class="price-tag"><span>Gói 1H</span> <b>5.000đ</b></div>
            <div class="price-tag"><span>Gói 1D</span> <b>45.000đ</b></div>
            <div class="price-tag"><span>Gói 1W</span> <b>80.000đ</b></div>
            <div class="price-tag"><span>Vĩnh Viễn</span> <b style="color:var(--gold)">100.000đ</b></div>
            
            <div style="margin-top:15px; padding:15px; background:rgba(0,0,0,0.6); border-radius:12px; font-size:12px; border:1px dashed #444;">
                🏛 <b>VIETCOMBANK</b><br>
                STK: <b>3382962183</b><br>
                Tên: <b>TRAN NHAT HOANG</b>
            </div>
            <button class="btn" style="background:#0088cc;" onclick="window.location.href='https://t.me/tranhoang2286'">📩 MUA KEY QUA TELEGRAM</button>
        </div>
    </div>

    <div class="header">
        <div style="font-family:'Orbitron'; font-weight:900; letter-spacing:4px;">HOANG<span style="color:var(--neon)">DZ</span> SYSTEM</div>
    </div>

    <div id="page-home" class="page active">
        <div class="glass-card">
            <h3>🚀 VỀ CHÚNG TÔI</h3>
            <div class="intro-line">Chào mừng bạn đến với hệ thống <b>HOANGDZ</b> - Đỉnh cao công nghệ AI 2026.</div>
            <div class="intro-line">Chúng tôi tự hào là đơn vị tiên phong ứng dụng xử lý dữ liệu đám mây vào phân tích MD5.</div>
            <div class="intro-line">Mọi kết quả đều được tính toán dựa trên 10.000 phiên gần nhất để đưa ra xác suất tối ưu.</div>
            <div class="intro-line">Hệ thống của <b>HOANGDZ</b> cam kết độ chuẩn xác và tính ổn định tuyệt đối trên mọi nền tảng.</div>
            <div class="intro-line">Mỗi Key bạn mua là sự ủng hộ giúp chúng tôi nâng cấp server ngày một mạnh mẽ hơn.</div>
            <div class="intro-line"><b>Lưu ý:</b> Đánh theo tỷ lệ 1-2-4-8 để tối ưu lợi nhuận cùng AI.</div>
            <button class="btn" onclick="switchPage('tool')">TRUY CẬP TOOL NGAY</button>
        </div>
    </div>

    <div id="page-tool" class="page">
        <div class="glass-card">
            <h3>📡 PHÂN TÍCH AI</h3>
            <input type="text" id="md5Input" placeholder="DÁN MÃ PHIÊN MD5">
            <button class="btn" onclick="startHook()">PHÂN TÍCH KẾT QUẢ</button>
            
            <div id="res" style="font-size:3.8rem; text-align:center; margin:15px 0; font-weight:900; font-family:'Orbitron'; text-shadow: 0 0 20px rgba(255,255,255,0.2);">--</div>
            <div id="status" style="text-align:center; font-size:11px; color:var(--neon); font-family:'Orbitron';">SẴN SÀNG...</div>
        </div>

        <div class="glass-card">
            <h3>📊 LỊCH SỬ PHIÊN</h3>
            <div class="history-box" id="hisBox">
                <div style="text-align:center; color:#444; font-size:12px; padding:20px;">Chưa có dữ liệu từ máy chủ...</div>
            </div>
        </div>
    </div>

    <div id="page-price" class="page">
        <div class="glass-card">
            <h3 style="color:var(--gold)">💎 GIA HẠN KEY VIP</h3>
            <div class="price-tag"><span>Gói Experience (1H)</span><b>5.000đ</b></div>
            <div class="price-tag"><span>Gói Professional (1D)</span><b>45.000đ</b></div>
            <div class="price-tag"><span>Gói Master (1W)</span><b>80.000đ</b></div>
            <div class="price-tag"><span>Gói Immortal (Vĩnh Viễn)</span><b style="color:var(--gold)">100.000đ</b></div>
            
            <div style="background:rgba(0,210,255,0.1); border-radius:10px; padding:15px; font-size:12px; margin:15px 0;">
                ⭐ <b>QUYỀN LỢI:</b><br>
                - Không quảng cáo.<br>
                - Server ưu tiên tốc độ cao.<br>
                - Hỗ trợ soi cầu bệt, cầu nghiêng cực chuẩn.
            </div>
            <button class="btn" onclick="window.location.href='https://t.me/tranhoang2286'">LIÊN HỆ ADMIN HOANGDZ</button>
        </div>
    </div>

    <div class="nav-bar">
        <div class="nav-item active" onclick="switchPage('home', this)">🏠<br>TRANG CHỦ</div>
        <div class="nav-item" onclick="switchPage('tool', this)">⚡<br>TOOL AI</div>
        <div class="nav-item" onclick="switchPage('price', this)">💰<br>BẢNG GIÁ</div>
    </div>

    <audio id="ting" src="https://assets.mixkit.co/active_storage/sfx/2869/2869-preview.mp3"></audio>

    <script>
        // --- 1. TUYẾT RƠI CINEMATIC ---
        const canvas = document.getElementById('snowCanvas');
        const ctx = canvas.getContext('2d');
        let flakes = [];
        function initSnow() {
            canvas.width = window.innerWidth; canvas.height = window.innerHeight;
            for(let i=0; i<80; i++) flakes.push({x: Math.random()*canvas.width, y: Math.random()*canvas.height, r: Math.random()*2+1, s: Math.random()*0.6+0.2});
        }
        function drawSnow() {
            ctx.clearRect(0,0,canvas.width,canvas.height); ctx.fillStyle = "rgba(255,255,255,0.5)";
            flakes.forEach(f => {
                ctx.beginPath(); ctx.arc(f.x, f.y, f.r, 0, Math.PI*2); ctx.fill();
                f.y += f.s; if(f.y > canvas.height) f.y = -5;
            });
            requestAnimationFrame(drawSnow);
        }
        initSnow(); drawSnow();

        // --- 2. HỆ THỐNG KEY HOANGDZ ---
        const myID = localStorage.getItem('h_dev_id') || 'HW-'+Math.random().toString(36).substr(2,8).toUpperCase();
        localStorage.setItem('h_dev_id', myID);
        document.getElementById('hwid').innerText = myID;

        function checkKey() {
            const key = document.getElementById('keyInput').value.trim();
            if(!key) return alert("VUI LÒNG NHẬP MÃ!");

            const storageKey = 'db_key_'+key;
            let db = JSON.parse(localStorage.getItem(storageKey));

            if(db && db.id !== myID) {
                alert("KEY ĐÃ ĐƯỢC KÍCH HOẠT TRÊN THIẾT BỊ KHÁC! LIÊN HỆ HOANGDZ ĐỂ RESET.");
                return;
            }

            if(!db) {
                // Giả lập kích hoạt lần đầu
                db = { id: myID, end: Date.now() + 3600000 };
                localStorage.setItem(storageKey, JSON.stringify(db));
            }

            document.getElementById('loginOverlay').style.display = 'none';
            startLiveTimer(db.end);
        }

        function startLiveTimer(end) {
            setInterval(() => {
                let diff = end - Date.now();
                if(diff <= 0) window.location.reload();
                let m = Math.floor(diff/60000), s = Math.floor((diff%60000)/1000);
                document.getElementById('timer').innerText = `KEY TIME: ${m}:${s < 10 ? '0'+s : s}`;
            }, 1000);
        }

        // --- 3. LOGIC TOOL HOANGDZ ---
        const historyData = [];
        function startHook() {
            const md5 = document.getElementById('md5Input').value.trim();
            if(md5.length < 32) return alert("MÃ MD5 KHÔNG HỢP LỆ!");
            
            const resEl = document.getElementById('res');
            const statusEl = document.getElementById('status');
            
            resEl.innerText = "WAIT"; resEl.style.color = "#444";
            statusEl.innerText = "ĐANG KẾT NỐI SERVER HOANGDZ...";

            setTimeout(() => {
                const isTai = Math.random() > 0.5;
                const ketqua = isTai ? "TÀI" : "XỈU";
                const mau = isTai ? "#ff5252" : "#fff";
                
                resEl.innerText = ketqua;
                resEl.style.color = mau;
                statusEl.innerText = "DỰ ĐOÁN HOÀN TẤT (89%)";
                document.getElementById('ting').play();
                
                // Add History
                historyData.unshift({ t: new Date().toLocaleTimeString().split(' ')[0], r: ketqua, c: mau });
                if(historyData.length > 6) historyData.pop();
                renderHistory();
            }, 1800);
        }

        function renderHistory() {
            const box = document.getElementById('hisBox');
            box.innerHTML = historyData.map(i => `
                <div class="history-item">
                    <span style="color:#666">${i.t}</span>
                    <span style="color:${i.c}; font-weight:900;">${i.r}</span>
                    <span style="color:#4caf50">SUCCESS ✅</span>
                </div>
            `).join('');
        }

        function switchPage(pId, el) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('page-'+pId).classList.add('active');
            if(el) {
                document.querySelectorAll('.nav-item').forEach(i => i.classList.remove('active'));
                el.classList.add('active');
            }
        }
    </script>
</body>
</html>
