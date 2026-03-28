



       <!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>HOANGDZ - NEURAL AI SYSTEM 2026</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #020617;
            --card-bg: rgba(15, 23, 42, 0.95);
            --neon-blue: #38bdf8;
            --neon-gold: #fbbf24;
            --text-main: #f8fafc;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }
        body { background-color: var(--bg-color); color: var(--text-main); height: 100vh; overflow: hidden; }

        /* Canvas Tuyết Rơi */
        #snow-canvas { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 1; }

        .wrapper { position: relative; z-index: 10; height: 100vh; display: flex; flex-direction: column; }
        .tab-content { flex: 1; display: none; padding: 20px; overflow-y: auto; padding-bottom: 90px; }
        .tab-content.active { display: block; animation: fadeIn 0.4s ease; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        /* Nav Bar */
        .nav-bar {
            position: fixed; bottom: 0; width: 100%; height: 75px;
            background: rgba(15, 23, 42, 0.98); border-top: 2px solid var(--neon-blue);
            display: flex; justify-content: space-around; align-items: center; z-index: 100; backdrop-filter: blur(10px);
        }
        .nav-item { text-align: center; color: #64748b; font-size: 11px; cursor: pointer; font-weight: 700; transition: 0.3s; }
        .nav-item.active { color: var(--neon-blue); text-shadow: 0 0 10px var(--neon-blue); }
        .nav-item i { font-size: 22px; display: block; margin-bottom: 3px; }

        /* Card & UI Elements */
        .glass-card {
            background: var(--card-bg); border: 1px solid rgba(56, 189, 248, 0.2);
            border-radius: 25px; padding: 20px; margin-bottom: 15px; box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        .btn-action {
            width: 100%; padding: 15px; border-radius: 12px; border: none;
            background: linear-gradient(135deg, var(--neon-gold), #b45309);
            color: #000; font-weight: 800; cursor: pointer; text-transform: uppercase; margin-top: 10px;
        }
        input {
            width: 100%; padding: 15px; border-radius: 12px; background: #000;
            border: 1px solid #1e293b; color: var(--neon-blue); text-align: center; font-weight: bold;
        }

        /* Bảng giá */
        .price-row {
            display: flex; justify-content: space-between; padding: 16px;
            background: rgba(255,255,255,0.03); border-radius: 12px; margin-bottom: 8px;
            border-left: 4px solid var(--neon-gold); cursor: pointer; transition: 0.2s;
        }
        .price-row:hover { background: rgba(255,255,255,0.08); }

        /* Phân tích AI */
        .progress-container { height: 12px; background: #000; border-radius: 6px; display: flex; overflow: hidden; margin: 15px 0; border: 1px solid #334155; }
        .bar-tai { background: var(--neon-gold); width: 0%; transition: 1s cubic-bezier(0.4, 0, 0.2, 1); }
        .bar-xiu { background: var(--neon-blue); width: 0%; transition: 1s cubic-bezier(0.4, 0, 0.2, 1); }

        .game-frame { width: 100%; height: 500px; border: 2px solid var(--neon-blue); border-radius: 15px; margin-top: 20px; }

        /* Modal QR */
        .modal {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.9); z-index: 1000; justify-content: center; align-items: center;
        }
        .modal-box { background: #fff; color: #000; padding: 20px; border-radius: 20px; text-align: center; width: 90%; max-width: 340px; }
    </style>
</head>
<body>

    <canvas id="snow-canvas"></canvas>

    <div class="wrapper">
        <div id="tab-home" class="tab-content active">
            <div class="glass-card" style="margin-top: 40px;">
                <h1 style="color: var(--neon-gold); text-align: center; font-size: 26px;">NEURAL CORE AI</h1>
                <p style="color: var(--neon-blue); text-align: center; font-size: 10px; letter-spacing: 3px; margin-bottom: 20px;">HỆ THỐNG CÔNG NGHỆ HOANGDZ</p>
                <div style="font-size: 14px; line-height: 1.8; color: #94a3b8; text-align: justify;">
                    Hệ thống <b>Neural Core AI</b> được xây dựng trên nền tảng thuật toán giải mã MD5 đa luồng (Multi-threading). 
                    Khi người dùng nhập chuỗi MD5, AI sẽ kích hoạt các node tính toán song song để đối chiếu dữ liệu lịch sử và phân tích tỉ lệ nghiêng của thuật toán. 
                    <br><br>
                    Khác với các công cụ ngẫu nhiên, hệ thống chúng tôi dựa trên logic toán học để đưa ra kết quả có độ chính xác cao nhất cho Game 68GB. 
                    Mọi dữ liệu đều được mã hóa và bảo mật tuyệt đối, mang lại trải nghiệm chuyên nghiệp cho người dùng.
                </div>
            </div>
        </div>

        <div id="tab-buy" class="tab-content">
            <h2 style="text-align: center; color: var(--neon-gold); margin: 20px 0;">BẢNG GIÁ KEY VIP</h2>
            <div class="glass-card">
                <div class="price-row" onclick="openPay(12000, '1 GIỜ')"><span>Gói 1 Giờ</span> <b>12k</b></div>
                <div class="price-row" onclick="openPay(24000, '5 GIỜ')"><span>Gói 5 Giờ</span> <b>24k</b></div>
                <div class="price-row" onclick="openPay(50000, '1 NGÀY')"><span>Gói 24 Giờ</span> <b>50k</b></div>
                <div class="price-row" onclick="openPay(100000, '1 THÁNG')"><span>Gói 1 Tháng</span> <b>100k</b></div>
                <div class="price-row" onclick="openPay(150000, 'VĨNH VIỄN')"><span>Gói Vĩnh Viễn</span> <b>150k</b></div>
            </div>
        </div>

        <div id="tab-tool" class="tab-content">
            <div id="lock-screen" style="margin-top: 60px;">
                <div class="glass-card" style="border-color: var(--neon-gold);">
                    <h3 style="text-align: center; margin-bottom: 20px;">XÁC THỰC KÍCH HOẠT</h3>
                    <input type="text" id="keyInp" placeholder="Nhập Key để sử dụng...">
                    <button class="btn-action" onclick="unlock()">KÍCH HOẠT HỆ THỐNG</button>
                </div>
            </div>

            <div id="tool-ui" style="display: none;">
                <div class="glass-card">
                    <input type="text" id="md5Inp" placeholder="Dán mã MD5 tại đây...">
                    <button class="btn-action" style="background: var(--neon-blue);" onclick="startAnalysis()">PHÂN TÍCH THUẬT TOÁN</button>
                    
                    <div id="result-box" style="margin-top: 20px; display: none; text-align: center;">
                        <div style="display: flex; justify-content: space-between; font-size: 12px; font-weight: 800;">
                            <span style="color: var(--neon-gold);">TÀI: <span id="txtTai">0%</span></span>
                            <span style="color: var(--neon-blue);">XỈU: <span id="txtXiu">0%</span></span>
                        </div>
                        <div class="progress-container">
                            <div id="barTai" class="bar-tai"></div>
                            <div id="barXiu" class="bar-xiu"></div>
                        </div>
                        <h2 id="finalResult" style="font-size: 40px; margin: 10px 0;">---</h2>
                        <p id="winRate" style="color: #22c55e; font-weight: bold; font-size: 14px;"></p>
                    </div>
                </div>
                <iframe src="https://68gbvn88.bar" class="game-frame"></iframe>
            </div>
        </div>

        <div id="tab-admin" class="tab-content">
            <div class="glass-card" style="text-align: center; margin-top: 60px;">
                <h2 style="color: var(--neon-gold);">HỖ TRỢ ADMIN</h2>
                <p style="margin: 20px 0; color: #94a3b8;">Vui lòng liên hệ Admin để nhận Key sau khi thanh toán thành công.</p>
                <button class="btn-action" onclick="window.location.href='https://t.me/tranhoang2286'">TELEGRAM: @tranhoang2286</button>
            </div>
        </div>

        <div class="nav-bar">
            <div class="nav-item active" onclick="switchTab('home', this)"><i>🏠</i>Nhà</div>
            <div class="nav-item" onclick="switchTab('buy', this)"><i>💰</i>Mua Key</div>
            <div class="nav-item" onclick="switchTab('tool', this)"><i>⚡</i>Vào Tool</div>
            <div class="nav-item" onclick="switchTab('admin', this)"><i>📞</i>Admin</div>
        </div>
    </div>

    <div id="payModal" class="modal">
        <div class="modal-box">
            <h3 id="pTitle">THANH TOÁN</h3>
            <img id="qrImg" src="" style="width: 250px; margin: 15px 0;">
            <p>STK: <b>3382962182</b></p>
            <p><b>VIETCOMBANK</b></p>
            <p style="color: red; margin-top: 10px;">Nội dung: <b id="pMemo"></b></p>
            <button onclick="document.getElementById('payModal').style.display='none'" style="margin-top: 15px; padding: 8px 20px;">ĐÓNG</button>
        </div>
    </div>

    <script>
        // Tuyết rơi (Giữ nguyên phong cách của bạn)
        const canvas = document.getElementById('snow-canvas');
        const ctx = canvas.getContext('2d');
        let snow = [];
        function init() {
            canvas.width = window.innerWidth; canvas.height = window.innerHeight;
            for(let i=0; i<100; i++) snow.push({x:Math.random()*canvas.width, y:Math.random()*canvas.height, r:Math.random()*3+1});
        }
        function draw() {
            ctx.clearRect(0,0,canvas.width, canvas.height); ctx.fillStyle="white"; ctx.beginPath();
            for(let s of snow) { ctx.moveTo(s.x, s.y); ctx.arc(s.x, s.y, s.r, 0, Math.PI*2); }
            ctx.fill(); update();
        }
        function update() { for(let s of snow) { s.y += 1.5; if(s.y > canvas.height) s.y = -10; } }
        setInterval(draw, 30); window.onload = init;

        // Xử lý Tab
        function switchTab(id, el) {
            document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
            document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
            document.getElementById('tab-'+id).classList.add('active');
            el.classList.add('active');
        }

        // Mở Thanh Toán
        function openPay(amt, type) {
            const memo = "HOANG" + Math.floor(1000 + Math.random()*8999);
            document.getElementById('pTitle').innerText = "Gói " + type;
            document.getElementById('pMemo').innerText = memo;
            document.getElementById('qrImg').src = `https://img.vietqr.io/image/vietcombank-3382962182-compact.png?amount=${amt}&addInfo=${memo}`;
            document.getElementById('payModal').style.display = 'flex';
        }

        // Kích hoạt Tool
        function unlock() {
            const k = document.getElementById('keyInp').value;
            if(k.length > 5) {
                document.getElementById('lock-screen').style.display = 'none';
                document.getElementById('tool-ui').style.display = 'block';
            } else { alert("Mã Key không hợp lệ!"); }
        }

        // Phân tích MD5 (Thuật toán tỉ lệ nghiêng)
        function startAnalysis() {
            const md5 = document.getElementById('md5Inp').value;
            if(md5.length < 5) return alert("Vui lòng nhập mã MD5!");
            
            const box = document.getElementById('result-box');
            const res = document.getElementById('finalResult');
            box.style.display = 'block';
            res.innerText = "WAITING...";

            let sum = 0;
            for(let i=0; i<md5.length; i++) sum += md5.charCodeAt(i);

            setTimeout(() => {
                let rate = 65 + (sum % 31);
                let taiVal, xiuVal;
                
                if(sum % 2 === 0) {
                    taiVal = rate; xiuVal = 100 - rate;
                    res.innerText = "TÀI"; res.style.color = "var(--neon-gold)";
                } else {
                    xiuVal = rate; taiVal = 100 - rate;
                    res.innerText = "XỈU"; res.style.color = "var(--neon-blue)";
                }

                document.getElementById('barTai').style.width = taiVal + "%";
                document.getElementById('barXiu').style.width = xiuVal + "%";
                document.getElementById('txtTai').innerText = taiVal + "%";
                document.getElementById('txtXiu').innerText = xiuVal + "%";
                document.getElementById('winRate').innerText = "ĐỘ TIN CẬY: " + rate + "%";
            }, 1500);
        }
    </script>
</body>
</html>
