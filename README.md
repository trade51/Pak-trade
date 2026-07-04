<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Pak Trade Global LLC - Premium Network Platform</title>
    <!-- Remix Icons integration for clean, professional app aesthetics -->
    <link href="https://cdn.jsdelivr.net/npm/remixicon@4.2.0/fonts/remixicon.css" rel="stylesheet">
    <style>
        /* Mobile-First Deep Premium Dark UI Theme */
        :root {
            --bg-base: #060913;
            --glass-surface: rgba(255, 255, 255, 0.03);
            --glass-card: rgba(255, 255, 255, 0.04);
            --glass-border: rgba(255, 255, 255, 0.06);
            --neon-green: #00e676;
            --promo-red: #ff3e3e;
            --text-muted: #7e8b9b;
            --gold-warning: #f59e0b;
            --glow-green: rgba(0, 230, 118, 0.15);
            --bottom-nav-bg: rgba(10, 14, 26, 0.85);
        }

        body {
            background-color: var(--bg-base);
            background-image: 
                radial-gradient(circle at 50% 0%, rgba(0, 230, 118, 0.04) 0%, transparent 60%),
                radial-gradient(circle at 50% 100%, rgba(245, 158, 11, 0.02) 0%, transparent 50%);
            color: #e2e8f0;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            margin: 0;
            padding: 0 0 85px 0; /* Clear space for fixed bottom nav bar */
            overflow-x: hidden;
            -webkit-tap-highlight-color: transparent;
        }

        /* 1. App Top Action Bar */
        .app-header {
            background: rgba(10, 14, 26, 0.6);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--glass-border);
            padding: 12px 16px;
            position: sticky;
            top: 0;
            z-index: 999;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .app-identity {
            display: flex;
            flex-direction: column;
        }

        .app-identity h1 {
            margin: 0;
            font-size: 16px;
            font-weight: 800;
            letter-spacing: -0.3px;
            color: #fff;
        }

        .app-identity span {
            font-size: 10px;
            color: var(--neon-green);
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 4px;
        }

        .app-logout-trigger {
            background: rgba(255, 62, 62, 0.1);
            border: 1px solid rgba(255, 62, 62, 0.2);
            color: #ff6b6b;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.2s ease;
        }
        .app-logout-trigger:active {
            transform: scale(0.9);
            background: var(--promo-red);
            color: #fff;
        }

        /* Running Ledger Bar */
        .live-ticker-wrap {
            background: rgba(0, 230, 118, 0.04);
            border-bottom: 1px solid rgba(0, 230, 118, 0.08);
            padding: 8px 0;
            overflow: hidden;
            white-space: nowrap;
        }

        .ticker-track {
            display: inline-block;
            animation: scrollTicker 25s linear infinite;
            font-size: 11px;
            font-weight: 600;
            color: var(--neon-green);
        }

        @keyframes scrollTicker {
            0% { transform: translate3d(100%, 0, 0); }
            100% { transform: translate3d(-100%, 0, 0); }
        }

        /* Container & Grid Setup */
        .app-body {
            padding: 16px;
            max-width: 600px; /* Optimized strictly for absolute mobile viewport clean look */
            margin: 0 auto;
        }

        /* 2. Pocket Balance Module (App Card Style) */
        .wallet-master-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.05) 0%, rgba(255,255,255,0.01) 100%);
            border: 1px solid var(--glass-border);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.2);
            border-radius: 24px;
            padding: 20px;
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
        }

        .wallet-master-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 150px;
            height: 150px;
            background: var(--glow-green);
            filter: blur(50px);
            border-radius: 50%;
            pointer-events: none;
        }

        .balance-label {
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--text-muted);
            margin: 0 0 4px 0;
        }

        .balance-value {
            font-size: 32px;
            font-weight: 800;
            color: #fff;
            margin: 0 0 20px 0;
        }

        .wallet-stats-sub-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            border-top: 1px solid rgba(255,255,255,0.06);
            padding-top: 15px;
        }

        .sub-stat-box h4 { margin: 0 0 2px 0; font-size: 10px; text-transform: uppercase; color: var(--text-muted); }
        .sub-stat-box p { margin: 0; font-size: 16px; font-weight: 700; color: #fff; }

        /* Quick Action Clickable Icons Group */
        .app-quick-actions {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-bottom: 25px;
        }

        .action-icon-btn {
            background: var(--glass-card);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 14px 8px;
            text-align: center;
            cursor: pointer;
            transition: background 0.2s, transform 0.2s;
        }

        .action-icon-btn:active {
            background: rgba(255,255,255,0.08);
            transform: scale(0.95);
        }

        .action-icon-btn i {
            font-size: 24px;
            display: block;
            margin-bottom: 6px;
        }

        .action-icon-btn span {
            font-size: 12px;
            font-weight: 600;
            color: #e2e8f0;
        }

        /* 3. Sliding Tab View Section Blocks */
        .app-view-panel {
            background: var(--glass-surface);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 16px;
            margin-bottom: 25px;
            display: none; /* Managed dynamically via JavaScript Tab routing */
        }

        .app-view-panel.panel-active {
            display: block;
            animation: fadeInApp 0.25s ease-out;
        }

        @keyframes fadeInApp {
            from { opacity: 0; transform: translateY(6px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .panel-heading {
            margin: 0 0 16px 0;
            font-size: 15px;
            font-weight: 700;
            color: #fff;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .app-input-element {
            margin-bottom: 14px;
        }

        .app-input-element label {
            display: block;
            font-size: 11px;
            color: var(--text-muted);
            margin-bottom: 4px;
            font-weight: 600;
        }

        .app-input-element input, .app-input-element select {
            width: 100%;
            background: #0b0f19;
            border: 1px solid var(--glass-border);
            padding: 12px;
            border-radius: 12px;
            color: #fff;
            box-sizing: border-box;
            font-size: 14px;
        }
        .app-input-element input:focus, .app-input-element select:focus {
            outline: none;
            border-color: var(--neon-green);
        }

        .app-btn-submit {
            width: 100%;
            padding: 14px;
            border-radius: 12px;
            border: none;
            font-size: 14px;
            font-weight: 700;
            cursor: pointer;
        }

        /* 4. Native App Style Grid Stream for Nodes */
        .app-section-title {
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 0.8px;
            color: var(--text-muted);
            margin: 10px 0 14px 0;
            font-weight: 700;
        }

        .mobile-node-list {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .mobile-node-item {
            background: var(--glass-card);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 12px;
            display: flex;
            align-items: center;
            gap: 12px;
            position: relative;
        }

        .node-img-thumb {
            width: 64px;
            height: 64px;
            border-radius: 12px;
            object-fit: cover;
        }

        .node-details-flex {
            flex: 1;
        }

        .node-details-flex h3 {
            margin: 0 0 4px 0;
            font-size: 14px;
            font-weight: 700;
            color: #fff;
        }

        .node-details-flex p {
            margin: 0;
            font-size: 11px;
            color: var(--text-muted);
        }

        .node-right-action {
            text-align: right;
        }

        .node-app-cost {
            font-size: 13px;
            font-weight: 800;
            display: block;
            margin-bottom: 6px;
        }

        .node-action-circle-btn {
            background: rgba(0, 230, 118, 0.1);
            border: 1px solid rgba(0, 230, 118, 0.2);
            color: var(--neon-green);
            width: 32px;
            height: 32px;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
        .mobile-node-item:active { background: rgba(255,255,255,0.06); }

        /* 5. Fixed Mobile Bottom Navigation Dock (Absolute Clickable Buttons) */
        .app-bottom-navbar {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: var(--bottom-nav-bg);
            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);
            border-top: 1px solid var(--glass-border);
            height: 65px;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            z-index: 1000;
            padding-bottom: env(safe-area-inset-bottom); /* iOS Swipe bar protection */
        }

        .nav-tab-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--text-muted);
            cursor: pointer;
            font-size: 11px;
            font-weight: 600;
            transition: color 0.2s;
        }

        .nav-tab-item i {
            font-size: 20px;
            margin-bottom: 2px;
        }

        .nav-tab-item.tab-active {
            color: var(--neon-green);
            text-shadow: 0 0 10px var(--glow-green);
        }
    </style>
</head>
<body>

    <!-- App System Header -->
    <header class="app-header">
        <div class="app-identity">
            <h1>Pak Trade Global LLC</h1>
            <span><i class="ri-checkbox-circle-fill"></i> Verified Corp Identity</span>
        </div>
        <div class="app-logout-trigger" onclick="logoutUser()">
            <i class="ri-logout-box-r-line"></i>
        </div>
    </header>

    <!-- Real-time Live Financial Data Stream Ticker -->
    <div class="live-ticker-wrap">
        <div class="ticker-track" id="payout-ticker">Stream initialized secure link array pool core...</div>
    </div>

    <!-- Main Container Shell for App Layout -->
    <div class="app-body">

        <!-- 1. Central Wallet Core Display Panel -->
        <div class="wallet-master-card">
            <p class="balance-label">Available Vault Balance</p>
            <h2 class="balance-value" id="user-balance">Rs. 0</h2>
            
            <div class="wallet-stats-sub-row">
                <div class="sub-stat-box">
                    <h4>Affiliate Yield</h4>
                    <p id="user-referrals" style="color: var(--gold-warning);">Rs. 0</p>
                </div>
                <div class="sub-stat-box">
                    <h4>Active Engines</h4>
                    <p id="active-nodes-count" style="color: var(--neon-green);">0 Units</p>
                </div>
            </div>
        </div>

        <!-- Quick Functional Shortcut Clickable Buttons Block -->
        <div class="app-quick-actions">
            <div class="action-icon-btn" onclick="switchTabRoute('deposit')">
                <i class="ri-arrow-down-circle-line" style="color: var(--neon-green);"></i>
                <span>Deposit</span>
            </div>
            <div class="action-icon-btn" onclick="switchTabRoute('withdraw')">
                <i class="ri-arrow-up-circle-line" style="color: var(--gold-warning);"></i>
                <span>Withdraw</span>
            </div>
            <div class="action-icon-btn" onclick="switchTabRoute('corporate')">
                <i class="ri-shield-user-line" style="color: #4da6ff;"></i>
                <span>Corporate</span>
            </div>
        </div>

        <!-- 2. Modular App Screen Tab Panels Matrix Routing Section -->
        <!-- DEPOSIT MODULE TAB VIEW -->
        <div id="panel-deposit" class="app-view-panel">
            <div class="panel-heading"><i class="ri-refund-2-line"></i> Secure Capital Deposit Gateway</div>
            <form onsubmit="handleDeposit(event)">
                <div class="app-input-element">
                    <label>Select Channel Method</label>
                    <select required>
                        <option value="easypaisa">EasyPaisa Instant System</option>
                        <option value="jazzcash">JazzCash Mobile Gateway</option>
                    </select>
                </div>
                <div class="app-input-element">
                    <label>Amount Value (PKR)</label>
                    <input type="number" id="dep-amount" min="200" placeholder="Minimum Rs. 200" required>
                </div>
                <div class="app-input-element">
                    <label>Transaction ID (Trx Proof Code)</label>
                    <input type="text" placeholder="Enter valid reference tracking ID" required>
                </div>
                <button class="app-btn-submit" type="submit" style="background: var(--neon-green); color: #060913;">Execute Deposit Request</button>
            </form>
        </div>

        <!-- WITHDRAWAL MODULE TAB VIEW -->
        <div id="panel-withdraw" class="app-view-panel">
            <div class="panel-heading"><i class="ri-bank-card-line"></i> Vault Liquidity Exit Route</div>
            <form onsubmit="handleWithdrawal(event)">
                <div class="app-input-element">
                    <label>Recipient Target Account Number</label>
                    <input type="text" placeholder="03XXXXXXXXX" required>
                </div>
                <div class="app-input-element">
                    <label>Exit Liquidity Value (PKR)</label>
                    <input type="number" id="wit-amount" min="100" placeholder="Minimum Rs. 100" required>
                </div>
                <small style="color: var(--promo-red); display:block; margin-bottom:12px; font-size:11px;">
                    * Notice: 10% system operations audit tax cut will apply during transit execution.
                </small>
                <button class="app-btn-submit" type="submit" style="background: var(--gold-warning); color: #060913;">Deploy Withdrawal Exit</button>
            </form>
        </div>

        <!-- CORPORATE CREDENTIAL DATA TAB VIEW -->
        <div id="panel-corporate" class="app-view-panel">
            <div class="panel-heading"><i class="ri-file-list-3-line"></i> SEC Corporate Disclosures</div>
            <div style="font-size: 12px; line-height: 1.6; color: var(--text-muted);">
                <p><strong>Entity Name:</strong> Pak Trade Global LLC</p>
                <p><strong>System Core Registry Identifier:</strong> #LLC-2026-9941</p>
                <p><strong>Operational Infrastructure HQ:</strong> Suite 410, Tech Central Complex, Islamabad, Pakistan.</p>
                <p style="color: var(--gold-warning);">* Authorized distributed node ledger array pool certified compliance status: ACTIVE.</p>
            </div>
        </div>

        <!-- 3. Primary Mining Matrix Stream Stream Deck Layout -->
        <div class="app-section-title">Distributed Cloud Asset Arrays</div>
        <div class="mobile-node-list" id="nodes-mobile-deck"></div>

    </div>

    <!-- 4. PWA Styled Clickable Native Persistent Bottom App Navigation Dock Bar -->
    <nav class="app-bottom-navbar">
        <div class="nav-tab-item tab-active" id="tab-home" onclick="switchTabRoute('home')">
            <i class="ri-home-5-line"></i>
            <span>Home</span>
        </div>
        <div class="nav-tab-item" id="tab-deposit" onclick="switchTabRoute('deposit')">
            <i class="ri-wallet-3-line"></i>
            <span>Deposit</span>
        </div>
        <div class="nav-tab-item" id="tab-withdraw" onclick="switchTabRoute('withdraw')">
            <i class="ri-bank-line"></i>
            <span>Withdraw</span>
        </div>
        <div class="nav-tab-item" id="tab-corporate" onclick="switchTabRoute('corporate')">
            <i class="ri-government-line"></i>
            <span>Legal</span>
        </div>
    </nav>

    <!-- 5. Dynamic JavaScript Engine Architecture Module -->
    <script type="module">
        import { initializeApp } from "https://unpkg.com/firebase@10.8.0/firebase-app.js";
        import { getDatabase, ref, set, update, onValue } from "https://unpkg.com/firebase@10.8.0/firebase-database.js";
        import { getAuth, onAuthStateChanged, signOut } from "https://unpkg.com/firebase@10.8.0/firebase-auth.js";

        // Verified Fixed Firebase Credentials Configurations 
        const firebaseConfig = {
            apiKey: "AIzaSyBqtvNJW_HNv4H2EAzeAhNL-tiUjX1huEg",
            authDomain: "trade51-f64d5.firebaseapp.com",
            databaseURL: "https://trade51-f64d5-default-rtdb.firebaseio.com",
            projectId: "trade51-f64d5",
            storageBucket: "trade51-f64d5.firebasestorage.app",
            messagingSenderId: "38759095579",
            appId: "1:38759095579:web:013d72ab4b5183f99347be"
        };

        const app = initializeApp(firebaseConfig);
        const database = getDatabase(app);
        const auth = getAuth(app);

        let currentUserId = null;

        // Optimized 20+ Dynamic Core Matrix Dataset Array
        const pakTradeNodes = [
            { id: "p_a1", name: "Pod Alpha-1", cost: 200, dailyYield: 15, days: 30, img: "https://images.unsplash.com/photo-1639762681485-074b7f938ba0?w=200&q=80", cat: "normal" },
            { id: "p_a2", name: "Pod Alpha-2", cost: 400, dailyYield: 30, days: 30, img: "https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=200&q=80", cat: "normal" },
            { id: "p_a3", name: "Pod Alpha-3", cost: 600, dailyYield: 45, days: 30, img: "https://images.unsplash.com/photo-1563770660941-20978e870e26?w=200&q=80", cat: "normal" },
            { id: "p_a4", name: "Pod Alpha-4", cost: 800, dailyYield: 60, days: 30, img: "https://images.unsplash.com/photo-1581092335397-9583fe92d232?w=200&q=80",            { id: "p_a5", name: "Pod Alpha-5", cost: 1000, dailyYield: 80, days: 30, img: "https://images.unsplash.com/photo-1518770660439-4636190af475?w=200&q=80", cat: "normal" },
            { id: "p_a6", name: "Pod Alpha-6", cost: 1500, dailyYield: 125, days: 30, img: "https://images.unsplash.com/photo-1601524909162-be87252be298?w=200&q=80", cat: "normal" },
            { id: "p_a7", name: "Pod Alpha-7", cost: 2000, dailyYield: 170, days: 30, img: "https://images.unsplash.com/photo-1547082299-de196ea013d6?w=200&q=80", cat: "normal" },
            { id: "r_s1", name: "Rig Stratum-1 [PROMO]", cost: 3000, dailyYield: 300, days: 10, img: "https://images.unsplash.com/photo-1640340434855-6084b1f4901c?w=200&q=80", cat: "special" },
            { id: "r_s2", name: "Rig Stratum-2 [PROMO]", cost: 4000, dailyYield: 360, days: 12, img: "https://images.unsplash.com/photo-1624996379697-f01d168b1a52?w=200&q=80", cat: "special" },
            { id: "r_s3", name: "Rig Stratum-3 [PROMO]", cost: 5000, dailyYield: 420, days: 15, img: "https://images.unsplash.com/photo-1544383835-bda2bc66a55d?w=200&q=80", cat: "special" },
            { id: "r_s4", name: "Rig Stratum-4 [PROMO]", cost: 7000, dailyYield: 600, days: 15, img: "https://images.unsplash.com/photo-1591453089816-0fbb971b454c?w=200&q=80", cat: "special" },
            { id: "r_s5", name: "Rig Stratum-5 [PROMO]", cost: 10000, dailyYield: 900, days: 15, img: "https://images.unsplash.com/photo-1600132806370-bf17e65e942f?w=200&q=80", cat: "special" },
            { id: "r_s6", name: "Rig Stratum-6 [PROMO]", cost: 15000, dailyYield: 1400, days: 15, img: "https://images.unsplash.com/photo-1587560699334-bea93391dcef?w=200&q=80", cat: "special" },
            { id: "r_s7", name: "Rig Stratum-7 [PROMO]", cost: 20000, dailyYield: 2000, days: 15, img: "https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=200&q=80", cat: "special" },
            { id: "m_qc1", name: "Matrix Quantum-Core", cost: 100000, dailyYield: 8500, days: 45, img: "https://images.unsplash.com/photo-1607604276583-eef5d076aa5f?w=200&q=80", cat: "exclusive" },
            { id: "m_qc2", name: "Quantum-Core V2", cost: 150000, dailyYield: 13500, days: 45, img: "https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?w=200&q=80", cat: "exclusive" },
            { id: "m_qc3", name: "Quantum-Core Ultra", cost: 200000, dailyYield: 19000, days: 45, img: "https://images.unsplash.com/photo-1504639725590-34d0984388bd?w=200&q=80", cat: "exclusive" },
            { id: "m_qc4", name: "Apex Nebula Cluster", cost: 300000, dailyYield: 30000, days: 50, img: "https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=200&q=80", cat: "exclusive" },
            { id: "m_qc5", name: "Titan Server Array", cost: 400000, dailyYield: 42000, days: 50, img: "https://images.unsplash.com/photo-1535141192574-5d4897c13636?w=200&q=80", cat: "exclusive" },
            { id: "m_qc6", name: "Supernova Grid-Pool", cost: 500000, dailyYield: 55000, days: 50, img: "https://images.unsplash.com/photo-1579546929518-9e396f3cc809?w=200&q=80", cat: "exclusive" },
            { id: "m_qc7", name: "Infinity Ledger Mainframe", cost: 1000000, dailyYield: 120000, days: 60, img: "https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?w=200&q=80", cat: "exclusive" }
        ];

        onAuthStateChanged(auth, (user) => {
            if (user) {
                currentUserId = user.uid;
                trackAppWalletRef(currentUserId);
            } else {
                currentUserId = null;
                document.getElementById('user-balance').innerText = "Rs. 0";
                document.getElementById('user-referrals').innerText = "Rs. 0";
                document.getElementById('active-nodes-count').innerText = "0 Units";
            }
        });

        function trackAppWalletRef(uid) {
            const walletRef = ref(database, 'users/' + uid);
            onValue(walletRef, (snap) => {
                const data = snap.val();
                if (data) {
                    document.getElementById('user-balance').innerText = `Rs. ${data.balance.toLocaleString()}`;
                    document.getElementById('user-referrals').innerText = `Rs. ${data.referralEarnings.toLocaleString()}`;
                    document.getElementById('active-nodes-count').innerText = `${data.leasedCount} Units`;
                    window.currentUserWallet = data;
                } else {
                    set(walletRef, { balance: 1000, referralEarnings: 0, leasedCount: 0, email: auth.currentUser.email });
                }
            });
        }

        window.switchTabRoute = function(targetPanel) {
            document.querySelectorAll('.app-view-panel').forEach(p => p.classList.remove('panel-active'));
            document.querySelectorAll('.nav-tab-item').forEach(t => t.classList.remove('tab-active'));
            if (targetPanel !== 'home') {
                const panel = document.getElementById(`panel-${targetPanel}`);
                if (panel) panel.classList.add('panel-active');
            }
            const activeTabButton = document.getElementById(`tab-${targetPanel}`);
            if (activeTabButton) activeTabButton.classList.add('tab-active');
        };

        window.handleDeposit = function(e) {
            e.preventDefault();
            if (!currentUserId) return alert("Session closed. Please login first sweetie!");
            const amt = parseInt(document.getElementById('dep-amount').value);
            const refDb = ref(database, 'users/' + currentUserId);
            update(refDb, { balance: (window.currentUserWallet?.balance || 0) + amt }).then(() => {
                alert(`Gateway Verified! Rs. ${amt} loaded to vault successfully.`);
                e.target.reset();
                switchTabRoute('home');
            });
        };

        window.handleWithdrawal = function(e) {
            e.preventDefault();
            if (!currentUserId) return alert("Session expired.");
            const amt = parseInt(document.getElementById('wit-amount').value);
            const currentBal = window.currentUserWallet?.balance || 0;
            if (amt > currentBal) return alert("Error: Account value limits exceeded.");
            const refDb = ref(database, 'users/' + currentUserId);
            update(refDb, { balance: currentBal - amt }).then(() => {
                alert(`Exit Route Deployed! Disbursed value (Net): Rs. ${amt * 0.90}`);
                e.target.reset();
                switchTabRoute('home');
            });
        };

        window.leaseProcessor = function(id, cost) {
            if (!currentUserId) return alert("Please authenticate first.");
            const currentBal = window.currentUserWallet?.balance || 0;
            if (currentBal < cost) return alert(`Insufficient capital pool reserve for asset acquisition.`);
            const refDb = ref(database, 'users/' + currentUserId);
            update(refDb, {
                balance: currentBal - cost,
                leasedCount: (window.currentUserWallet?.leasedCount || 0) + 1,
                referralEarnings: (window.currentUserWallet?.referralEarnings || 0) + (cost * 0.10)
            }).then(() => alert("Asset Engine online! Cloud mining lifecycle triggered."));
        };

        window.logoutUser = function() {
            signOut(auth).then(() => alert("Securely logged out, sweetie!"));
        };

        function buildMobileAppDeck() {
            const container = document.getElementById('nodes-mobile-deck');
            container.innerHTML = '';
            pakTradeNodes.forEach(node => {
                let badgeAccent = "var(--neon-green)";
                if (node.cat === 'special') badgeAccent = "var(--promo-red)";
                if (node.cat === 'exclusive') badgeAccent = "var(--gold-warning)";
                container.innerHTML += `
                    <div class="mobile-node-item">
                        <img src="${node.img}" class="node-img-thumb" alt="${node.name}">
                        <div class="node-details-flex">
                            <h3>${node.name}</h3>
                            <p>Daily: <span style="color: ${badgeAccent}; font-weight:700;">Rs. ${node.dailyYield}</span> • Cycle: ${node.days} Days</p>
                            <p style="font-size:10px; font-family:monospace; margin-top:2px;">Contract Net: Rs. ${node.dailyYield * node.days}</p>
                        </div>
                        <div class="node-right-action">
                            <span class="node-app-cost" style="color: ${badgeAccent};">Rs. ${node.cost}</span>
                            <div class="node-action-circle-btn" style="color:${badgeAccent}; border-color:${badgeAccent};" onclick="leaseProcessor('${node.id}', ${node.cost})">
                                <i class="ri-add-line"></i>
                            </div>
                        </div>
                    </div>`;
            });
        }

        window.onload = function() {
            buildMobileAppDeck();
            const sampleLogs = ['User 0312***551 withdrew Rs. 4,500', 'User 0333***902 leased Pod Alpha-3', 'User 0321***401 claimed Network Bounty'];
            document.getElementById('payout-ticker').innerHTML = sampleLogs.map(l => `• [NATIVE LOG] ${l} &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`).join('');
        };
    </script>
</body>
</html>
