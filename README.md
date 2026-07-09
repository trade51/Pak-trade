<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pak Trade | Ultimate Dashboard</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', sans-serif; background-color: #0a0e14; color: #ffffff; display: flex; min-height: 100vh; }
        .sidebar { width: 250px; background: #111827; padding: 20px; border-right: 1px solid #1f2937; }
        .logo { font-size: 1.8rem; font-weight: bold; color: #3b82f6; margin-bottom: 30px; }
        .sidebar li { padding: 15px; cursor: pointer; list-style: none; border-bottom: 1px solid #1f2937; }
        .main-content { flex: 1; padding: 40px; }
        .card { background: #111827; padding: 20px; border-radius: 10px; border: 1px solid #374151; margin-bottom: 20px; }
        .stats-cards { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; margin-bottom: 20px; }
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; }
        .node-card { background: #111827; padding: 15px; border-radius: 12px; border: 1px solid #374151; text-align: center; }
        .node-img { width: 100%; height: 120px; object-fit: cover; border-radius: 8px; margin-bottom: 10px; }
        .progress-bar { background: #374151; height: 8px; border-radius: 5px; margin: 10px 0; overflow: hidden; }
        .progress { background: #3b82f6; height: 100%; }
        button { padding: 10px 20px; background: #3b82f6; border: none; color: white; cursor: pointer; border-radius: 5px; width: 100%; font-weight: bold; }
        input { padding: 10px; width: 100%; margin: 10px 0; background: #0a0e14; border: 1px solid #374151; color: white; border-radius: 5px; }
    </style>
</head>
<body>

    <div class="sidebar">
        <div class="logo">Pak Trade</div>
        <ul>
            <li>Dashboard</li>
            <li>Market Data</li>
            <li id="logoutBtn" style="color: #ef4444;">Logout</li>
        </ul>
    </div>

    <div class="main-content">
        <!-- How it works -->
        <div class="card" style="border: 1px solid #3b82f6;">
            <h3>How Pak Trade Works</h3>
            <div style="display: flex; justify-content: space-around; margin-top: 15px; text-align: center;">
                <div>💳<p style="font-size: 0.7rem;">Deposit</p></div>
                <div>📈<p style="font-size: 0.7rem;">Mine</p></div>
                <div>💰<p style="font-size: 0.7rem;">Profit</p></div>
                <div>🏦<p style="font-size: 0.7rem;">Withdraw</p></div>
            </div>
        </div>

        <!-- Stats -->
        <div class="stats-cards">
            <div class="card"><h3>Balance</h3><p id="userBalance" style="color:#3b82f6; font-size:1.5rem; margin-top:10px;">$0.00</p></div>
            <div class="card"><h3>Security</h3><p style="color:#10b981; font-size:1.5rem; margin-top:10px;">SSL Secure</p></div>
            <div class="card"><h3>Status</h3><p style="color:#f59e0b; font-size:1.5rem; margin-top:10px;">Active</p></div>
        </div>

        <!-- Deposit -->
        <div class="card">
            <h3>Add Funds</h3>
            <input type="number" id="depositAmount" placeholder="Enter USD Amount">
            <button id="submitDeposit">Submit Request</button>
        </div>

        <!-- Mining Nodes -->
        <h3>Mining Machines</h3>
        <div class="grid" id="nodesContainer" style="margin-top:20px;"></div>
    </div>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/9.6.1/firebase-app.js";
        import { getAuth, signOut, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/9.6.1/firebase-auth.js";
        import { getDatabase, ref, onValue, push } from "https://www.gstatic.com/firebasejs/9.6.1/firebase-database.js";

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
        const auth = getAuth(app);
        const db = getDatabase(app);

        // Auto Generate 20 Nodes
        const container = document.getElementById('nodesContainer');
        for (let i = 1; i <= 20; i++) {
            container.innerHTML += `
                <div class="node-card">
                    <img src="https://images.unsplash.com/photo-1622737133649-6238383a6401?w=400" class="node-img">
                    <h4>Node #${i}</h4>
                    <p>Cost: $${i * 50} | Daily: $${i * 2}</p>
                    <div class="progress-bar"><div class="progress" style="width:${Math.random()*100}%"></div></div>
                    <p style="font-size:0.7rem;">Timer: 23h 12m</p>
                    <button onclick="alert('Machine #${i} Activated!')">Activate</button>
                </div>
            `;
        }

        // Firebase Auth & Data
        onAuthStateChanged(auth, (user) => {
            if (user) {
                onValue(ref(db, 'users/' + user.uid + '/balance'), (snap) => {
                    document.getElementById('userBalance').innerText = snap.val() ? `$${snap.val()}` : "$0.00";
                });
            } else { window.location.href = "login.html"; }
        });

        document.getElementById('submitDeposit').onclick = () => {
            const amt = document.getElementById('depositAmount').value;
            if(amt > 0) push(ref(db, 'deposit_requests/'), {userId: auth.currentUser.uid, amount: amt, status: 'pending'}).then(() => alert("Request Sent!"));
        };

        document.getElementById('logoutBtn').onclick = () => signOut(auth).then(() => location.href = "login.html");
    </script>
</body>
</html>
