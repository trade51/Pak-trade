<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pak Trade Global LLC - Premium Network Platform</title>
    <style>
        /* Modern Glassmorphic Dark UI Theme */
        :root {
            --bg-base: #070a13;
            --card-surface: rgba(255, 255, 255, 0.02);
            --card-border: rgba(255, 255, 255, 0.06);
            --neon-green: #00e676;
            --promo-red: #ff3e3e;
            --text-muted: #8492a6;
            --gold-warning: #f59e0b;
        }

        body {
            background-color: var(--bg-base);
            color: #e2e8f0;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }

        /* 1. Live Notification Scrolling Ticker */
        .live-ticker-wrap {
            background: rgba(0, 230, 118, 0.08);
            border-bottom: 1px solid rgba(0, 230, 118, 0.15);
            padding: 8px 0;
            overflow: hidden;
            white-space: nowrap;
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        .ticker-track {
            display: inline-block;
            animation: scrollTicker 25s linear infinite;
            font-size: 12px;
            font-weight: 600;
            color: var(--neon-green);
        }

        @keyframes scrollTicker {
            0% { transform: translate3d(100%, 0, 0); }
            100% { transform: translate3d(-100%, 0, 0); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* 2. User Stats Control Center */
        .dashboard-header {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 15px;
            margin-bottom: 35px;
        }

        .stat-box {
            background: var(--card-surface);
            border: 1px solid var(--card-border);
            border-radius: 16px;
            padding: 20px;
            text-align: center;
            position: relative;
        }

        .stat-box h4 { margin: 0; font-size: 12px; text-transform: uppercase; color: var(--text-muted); }
        .stat-box p { margin: 8px 0 0 0; font-size: 24px; font-weight: 800; color: #fff; }

        /* 3. Operational Forms Flex Section */
        .operations-panel {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .op-card {
            background: rgba(255, 255, 255, 0.01);
            border: 1px solid var(--card-border);
            border-radius: 16px;
            padding: 20px;
        }

        .op-card h3 { margin-top: 0; font-size: 16px; color: #fff; display: flex; align-items: center; gap: 8px; }
        
        .input-group {
            margin-bottom: 15px;
        }

        .input-group label { display: block; font-size: 11px; color: var(--text-muted); margin-bottom: 5px; }
        
        .input-group input, .input-group select {
            width: 100%;
            background: rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.1);
            padding: 10px;
            border-radius: 8px;
            color: #fff;
            box-sizing: border-box;
            font-size: 13px;
        }

        .input-group input:focus { border-color: var(--neon-green); outline: none; }

        .form-action-btn {
            width: 100%;
            background: var(--neon-green);
            color: #070a13;
            border: none;
            padding: 12px;
            border-radius: 8px;
            font-weight: 700;
            cursor: pointer;
            transition: 0.2s;
        }
        .form-action-btn:hover { opacity: 0.9; }

        /* 4. Nodes Store Engine Layout */
        .section-title {
            font-size: 20px;
            font-weight: 700;
            margin: 40px 0 20px 0;
            border-left: 4px solid var(--neon-green);
            padding-left: 10px;
        }

        #nodes-display-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(270px, 1fr));
            gap: 20px;
        }

        .node-premium-card {
            background: var(--card-surface);
            border: 1px solid var(--card-border);
            border-radius: 20px;
            overflow: hidden;
            transition: 0.3s;
        }
        .node-premium-card:hover { transform: translateY(-4px); }

        .promo-active-border { border-color: rgba(255, 62, 62, 0.3) !important; }

        .node-image-wrap { position: relative; width: 100%; height: 140px; }
        .node-image-wrap img { width: 100%; height: 100%; object-fit: cover; }
        
        .node-badge-cost {
            position: absolute; bottom: 10px; right: 10px;
            color: #070a13; font-weight: 800; padding: 5px 10px;
            border-radius: 8px; font-size: 12px;
        }

        .promo-ribbon {
            position: absolute; top: 10px; left: 10px; background: var(--promo-red);
            color: #fff; font-size: 9px; font-weight: 900; padding: 3px 6px; border-radius: 4px;
        }

        .node-meta-body { padding: 15px; }
        .node-meta-body h3 { margin: 0 0 10px 0; font-size: 16px; color: #fff; }
        .meta-row { display: flex; justify-content: space-between; font-size: 12px; color: var(--text-muted); margin-bottom: 6px; }

        .timer-box {
            display: flex; align-items: center; gap: 8px;
            background: rgba(0, 0, 0, 0.2); padding: 8px; border-radius: 10px; margin: 12px 0;
        }
        .timer-text-wrap p { margin: 0; font-size: 12px; font-weight: 700; color: var(--gold-warning); font-family: monospace; }
        
        .node-action-btn {
            width: 100%; background: transparent; border: 1px solid rgba(0,230,118,0.3);
            color: var(--neon-green); padding: 10px; border-radius: 10px; font-weight: 700; font-size: 12px; cursor: pointer;
        }
        .node-action-btn:hover { background: var(--neon-green); color: #070a13; }
    </style>
</head>
<body>

    <!-- 1. Real-time Live Ticker Module -->
    <div class="live-ticker-wrap">
        <div class="ticker-track" id="payout-ticker">
            Loading distributed ledger tracks...
        </div>
    </div>

    <div class="container">
        <header style="margin-bottom: 30px;">
            <h2 style="margin: 0; color: #fff;">Pak Trade Global LLC</h2>
            <small style="color: var(--text-muted);">Decentralized Deployment Terminal: trade51.github.io/Pak-trade/</small>
        </header>

        <!-- 2. Wallet Core Dashboard -->
        <div class="dashboard-header">
            <div class="stat-box">
                <h4>Available Capital Balance</h4>
                <p id="user-balance">Rs. 0</p>
            </div>
            <div class="stat-box">
                <h4>Total Affiliate Rewards</h4>
                <p id="user-referrals">Rs. 0</p>
            </div>
            <div class="stat-box">
                <h4>Active Running Nodes</h4>
                <p id="active-nodes-count">0</p>
            </div>
        </div>

        <!-- 3. Gateway Interaction Blocks -->
        <div class="operations-panel">
            <!-- Deposit Interface -->
            <div class="op-card">
                <h3>📥 Capital Gateway (Deposit)</h3>
                <form id="deposit-form" onsubmit="handleDeposit(event)">
                    <div class="input-group">
                        <label>Select Channel</label>
                        <select required>
                            <option value="easypaisa">EasyPaisa (03XX-XXXXXXX)</option>
                            <option value="jazzcash">JazzCash (03XX-XXXXXXX)</option>
                        </select>
                    </div>
                    <div class="input-group">
                        <label>Exact Value Amount (PKR)</label>
                        <input type="number" min="200" placeholder="Minimum Rs. 200" id="dep-amount" required>
                    </div>
                    <div class="input-group">
                        <label>Transaction ID (TRX ID Reference)</label>
                        <input type="text" placeholder="Enter 11-digit Transaction ID" required>
                    </div>
                    <button class="form-action-btn" type="submit">Submit Deposit Request</button>
                </form>
            </div>

            <!-- Withdrawal Interface with 10% System Tax Mapping -->
            <div class="op-card">
                <h3>📤 Secure Vault Exit (Withdrawal)</h3>
                <form id="withdraw-form" onsubmit="handleWithdrawal(event)">
                    <div class="input-group">
                        <label>Destination Account Number</label>
                        <input type="text" placeholder="03XXXXXXXXX" required>
                    </div>
                    <div class="input-group">
                        <label>Exit Amount (PKR)</label>
                        <input type="number" min="100" placeholder="Minimum Rs. 100" id="wit-amount" required>
                    </div>
                    <small style="color: var(--promo-red); display:block; margin-bottom:12px; font-size:11px;">
                        * Note: 10% Safe Operational Tax will be cut automatically from this transit.
                    </small>
                    <button class="form-action-btn" style="background: var(--gold-warning);" type="submit">Initialize Liquidity Exit</button>
                </form>
            </div>
        </div>

        <!-- 4. Dynamic Cloud Computing Node Matrix Grid -->
        <div class="section-title">Available Cloud Mining Arrays</div>
        <div id="nodes-display-grid"></div>
    </div>

    <script>
        // Data Store Matrices Configuration Initialization
        let userWallet = JSON.parse(localStorage.getItem('pakTradeWallet')) || { balance: 1000, referralEarnings: 0, leasedCount: 0 };
        
        const pakTradeNodes = [
            { id: "p_a1", name: "Pod Alpha-1", cost: 200, dailyYield: 15, days: 30, img: "https://images.unsplash.com/photo-1639762681485-074b7f938ba0?w=400&q=80", cat: "normal" },
            { id: "p_a2", name: "Pod Alpha-2", cost: 400, dailyYield: 30, days: 30, img: "https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=400&q=80", cat: "normal" },
            { id: "p_a3", name: "Pod Alpha-3", cost: 600, dailyYield: 45, days: 30, img: "https://images.unsplash.com/photo-1563770660941-20978e870e26?w=400&q=80", cat: "normal" },
            { id: "r_s1", name: "Rig Stratum-1 [PROMO]", cost: 3000, dailyYield: 300, days: 10, img: "https://images.unsplash.com/photo-1640340434855-6084b1f4901c?w=400&q=80", cat: "special" },
            { id: "r_s2", name: "Rig Stratum-2 [PROMO]", cost: 4000, dailyYield: 360, days: 12, img: "https://images.unsplash.com/photo-1624996379697-f01d168b1a52?w=400&q=80", cat: "special" },
            { id: "r_s3", name: "Rig Stratum-3 [PROMO]", cost: 5000, dailyYield: 420, days: 15, img: "https://images.unsplash.com/photo-1544383835-bda2bc66a55d?w=400&q=80", cat: "special" },
            { id: "m_qc", name: "Matrix Quantum-Core", cost: 100000, dailyYield: 8500, days: 45, img: "https://images.unsplash.com/photo-1607604276583-eef5d076aa5f?w=400&q=80", cat: "exclusive" }
        ];

        function syncDOMCounters() {
            document.getElementById('user-balance').innerText = `Rs. ${userWallet.balance.toLocaleString()}`;
            document.getElementById('user-referrals').innerText = `Rs. ${userWallet.referralEarnings.toLocaleString()}`;
            document.getElementById('active-nodes-count').innerText = userWallet.leasedCount;
            localStorage.setItem('pakTradeWallet', JSON.stringify(userWallet));
        }

        // Live Dynamic Ticker Simulation Array Generation
        function buildLiveTickerSystem() {
            const users = ['0301','0345','0321','0312','0333','0306'];
            const tasks = [
                'successfully withdrew Rs. 2,400', 
                'leased Rig Stratum-1 [PROMO] node', 
                'added Rs. 5,000 capital', 
                'claimed Level-1 affiliate bonus of Rs. 600'
            ];
            let tickerString = "";
            for(let i=0; i<15; i++) {
                let randUser = users[Math.floor(Math.random()*users.length)] + "***" + Math.floor(100+Math.random()*900);
                let randTask = tasks[Math.floor(Math.random()*tasks.length)];
                tickerString += `• [⚡ LOG] User ${randUser} ${randTask} &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`;
            }
            document.getElementById('payout-ticker').innerHTML = tickerString;
        }

        // Form Submission Logic
        function handleDeposit(e) {
            e.preventDefault();
            const amt = parseInt(document.getElementById('dep-amount').value);
            alert(`Gateway Notification:\nYour deposit tracking record of Rs. ${amt} has been submitted. Admin review processing delay can take up to 30 mins.`);
            userWallet.balance += amt; // Local simulated addition
            syncDOMCounters();
            e.target.reset();
        }

        function handleWithdrawal(e) {
            e.preventDefault();
            const amt = parseInt(document.getElementById('wit-amount').value);
            if(amt > userWallet.balance) {
                alert("Error: Insufficient Vault Funds for transition processing.");
                return;
            }
            const netExitValue = amt * 0.90; // Deducting 10% Owner Safety Fee
            userWallet.balance -= amt;
            syncDOMCounters();
            alert(`Withdrawal Initialized!\nRequested: Rs. ${amt}\nNet Paid (After 10% Platform Tax): Rs. ${netExitValue}\nProcessing Loop Status: PENDING.`);
            e.target.reset();
        }

        // Store Layout Render Grid Module Engine
        function renderPakTradeStore() {
            const gridTarget = document.getElementById('nodes-display-grid');
            gridTarget.innerHTML = ''; 

            pakTradeNodes.forEach((node) => {
                const totalProfit = node.dailyYield * node.days;
                const isSpecial = node.cat === "special";
                const badgeColor = isSpecial ? "var(--promo-red)" : "var(--neon-green)";
                
                const cardHtml = `
                    <div class="node-premium-card ${isSpecial ? 'promo-active-border' : ''}">
                        <div class="node-image-wrap">
                            ${isSpecial ? `<span class="promo-ribbon">HOT Promo</span>` : ''}
                            <img src="${node.img}" alt="${node.name}">
                            <span class="node-badge-cost" style="background: ${badgeColor};">
                                Rs. ${node.cost.toLocaleString()}
                            </span>
                        </div>
                        <div class="node-meta-body">
                            <h3>${node.name}</h3>
                            <div class="meta-row"><span>Daily Payout:</span><b style="color: ${badgeColor};">Rs. ${node.dailyYield}</b></div>
                            <div class="meta-row"><span>Total Matrix Net:</span><b style="color: #fff;">Rs. ${totalProfit}</b></div>
                            <div class="meta-row"><span>Cycle Lifetime:</span><span class="cycle-tag">${node.days} Days Contract</span></div>
                            <div class="timer-box">
                                <span class="timer-icon">${isSpecial ? '🔥' : '⚡'}</span>
                                <div class="timer-text-wrap">
                                    <p class="realtime-clock-node">24:00:00</p>
                                </div>
                            </div>
                            <button class="node-action-btn" style="${isSpecial ? 'border-color: var(--promo-red); color: var(--promo-red);' : ''}" 
                                    onclick="leaseProcessor('${node.id}', ${node.cost})">
                                Lease Node Engine
                            </button>
                        </div>
                    </div>
                `;
                gridTarget.innerHTML += cardHtml;
            });
        }

        function leaseProcessor(id, cost) {
            if(userWallet.balance < cost) {
                alert(`Insufficient Balance!\nRequired amount: Rs. ${cost}\nPlease use the Capital Gateway to load funds.`);
                return;
            }
            userWallet.balance -= cost;
            userWallet.leasedCount += 1;
            
            // Dynamic Referral Bonus Mapping simulation (10% back to Affiliate Pool)
            const refBonus = cost * 0.10;
            userWallet.referralEarnings += refBonus;
            
            syncDOMCounters();
            alert(`Node successfully deployed to environment infrastructure array!\n10% Referral Bonus generated: Rs. ${refBonus}`);
        }

        function runClockLoop() {
            setInterval(() => {
                const clocks = document.querySelectorAll('.realtime-clock-node');
                const now = new Date();
                const timeString = `${(23 - now.getHours()).toString().padStart(2,'0')}:${(59 - now.getMinutes()).toString().padStart(2,'0')}:${(59 - now.getSeconds()).toString().padStart(2,'0')}`;
                clocks.forEach(c => c.innerText = timeString);
            }, 1000);
        }

        window.onload = function() {
            syncDOMCounters();
            buildLiveTickerSystem();
            renderPakTradeStore();
            runClockLoop();
        };
    </script>
</body>
</html>
