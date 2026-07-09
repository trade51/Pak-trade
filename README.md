<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PAK TRADE | PRO TERMINAL</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@200;400;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Plus Jakarta Sans', sans-serif; background: #020617; color: #f8fafc; }
        .glass { background: rgba(15, 23, 42, 0.6); backdrop-filter: blur(20px); border: 1px solid rgba(255, 255, 255, 0.08); }
        .node-hover:hover { border-color: #3b82f6; transform: translateY(-5px); }
        ::-webkit-scrollbar { width: 4px; }
        ::-webkit-scrollbar-thumb { background: #3b82f6; }
    </style>
</head>
<body class="pb-24">

    <!-- Navbar -->
    <nav class="max-w-7xl mx-auto p-6 flex justify-between items-center">
        <h1 id="adminLogo" class="text-2xl font-black text-blue-500 cursor-pointer">PAK TRADE<span class="text-white">.PRO</span></h1>
        <button onclick="claimBonus()" id="bonusBtn" class="bg-yellow-500/10 text-yellow-500 px-4 py-2 rounded-xl text-xs font-bold border border-yellow-500/20">DAILY BONUS</button>
    </nav>

    <main class="max-w-7xl mx-auto p-6 space-y-8">
        <!-- Stats -->
        <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
            <div class="glass p-8 rounded-[2rem] lg:col-span-2">
                <p class="text-slate-400 text-xs uppercase tracking-widest">Asset Value</p>
                <h2 id="balance" class="text-5xl font-extrabold my-2">0.000000</h2>
            </div>
            <div class="glass p-6 rounded-[2rem] flex flex-col justify-center">
                <p class="text-slate-400 text-xs">Weekly Salary</p>
                <h3 class="text-xl font-bold text-blue-400">3,500 PKR</h3>
            </div>
            <div class="glass p-6 rounded-[2rem] flex flex-col justify-center">
                <p class="text-slate-400 text-xs">Monthly Salary</p>
                <h3 class="text-xl font-bold text-green-400">15,000 PKR</h3>
            </div>
        </div>

        <!-- 20+ Nodes Grid -->
        <h3 class="text-2xl font-bold">Mining Infrastructure</h3>
        <div id="nodeGrid" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-4"></div>

        <!-- Live Activity -->
        <div class="glass p-6 rounded-[2rem]">
            <h3 class="font-bold mb-4">Network Activity</h3>
            <div id="txTable" class="space-y-3 h-48 overflow-y-auto"></div>
        </div>
    </main>

    <script>
        // Nodes Data
        const nodeGrid = document.getElementById("nodeGrid");
        for(let i=1; i<=20; i++) {
            nodeGrid.innerHTML += `
            <div class="glass p-5 rounded-2xl node-hover transition-all duration-300">
                <i data-lucide="cpu" class="text-blue-500 mb-3"></i>
                <h4 class="text-sm font-bold">Node ${i}</h4>
                <p class="text-[10px] text-slate-400">Profit: ${i * 20} PKR</p>
                <button class="w-full mt-3 py-2 bg-white text-black text-[10px] font-bold rounded-lg hover:bg-blue-500">BUY</button>
            </div>`;
        }
        lucide.createIcons();

        // Bonus & Mining Logic
        function claimBonus() {
            let b = parseFloat(document.getElementById("balance").innerText);
            document.getElementById("balance").innerText = (b + 50).toFixed(6);
            document.getElementById("bonusBtn").disabled = true;
            alert("Bonus Claimed, sweetie!");
        }

        setInterval(() => {
            let b = parseFloat(document.getElementById("balance").innerText);
            document.getElementById("balance").innerText = (b + 0.0005).toFixed(6);
        }, 1000);

        // Fake Transactions
        const txTable = document.getElementById("txTable");
        for(let i=0; i<20; i++) {
            txTable.innerHTML += `<div class="flex justify-between text-xs border-b border-white/5 pb-2"><span>User${i}***</span><span class="text-green-500">Deposited 500</span></div>`;
        }

        // Admin Access
        let t=0; document.getElementById("adminLogo").onclick = () => {
            t++; if(t>=5 && prompt("Access Key:")=="5426") alert("Welcome, Muhammad Nazim. System Override Active.");
        };
    </script>
</body>
</html>
