<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pak Trade | Premium</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;700;900&display=swap');
        body { font-family: 'Outfit', sans-serif; background: #0a0a0a; color: #fff; }
        .glass { background: rgba(255, 255, 255, 0.02); backdrop-filter: blur(20px); border: 1px solid rgba(255, 255, 255, 0.05); }
        .gradient-text { background: linear-gradient(90deg, #3b82f6, #8b5cf6); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .node-card { transition: transform 0.3s ease, border 0.3s ease; }
        .node-card:hover { transform: translateY(-5px); border: 1px solid #3b82f6; }
        .app-container { max-width: 480px; margin: auto; min-height: 100vh; position: relative; padding-bottom: 100px; }
    </style>
</head>
<body>

<div class="app-container">
    <!-- Header -->
    <header class="p-6 flex justify-between items-center">
        <h1 id="adminLogo" class="text-2xl font-black gradient-text tracking-tighter cursor-pointer">PAK TRADE</h1>
        <div class="w-10 h-10 rounded-full bg-blue-600/20 flex items-center justify-center border border-blue-500/30">M</div>
    </header>

    <!-- Main Balance Card -->
    <div class="px-6 py-2">
        <div class="glass p-8 rounded-[2rem] text-center shadow-[0_0_50px_-12px_rgba(59,130,246,0.3)]">
            <p class="text-gray-500 text-xs tracking-widest uppercase">Available Balance</p>
            <h2 id="balance" class="text-5xl font-black mt-2">0.000000</h2>
            <div class="mt-6 flex justify-center gap-4">
                <button class="bg-blue-600 px-6 py-2 rounded-full font-bold text-sm hover:scale-105 transition">DEPOSIT</button>
                <button class="bg-white/10 px-6 py-2 rounded-full font-bold text-sm hover:scale-105 transition">WITHDRAW</button>
            </div>
        </div>
    </div>

    <!-- Nodes Section -->
    <div class="px-6 py-8">
        <h3 class="text-lg font-bold mb-6 flex items-center gap-2">
            <span class="w-2 h-6 bg-blue-600 rounded-full"></span> Active Nodes
        </h3>
        <div id="machineGrid" class="grid grid-cols-1 gap-6"></div>
    </div>

    <!-- Navigation -->
    <nav class="fixed bottom-6 left-1/2 -translate-x-1/2 w-[90%] max-w-[400px] glass rounded-full p-2 flex justify-around items-center">
        <button class="p-3 text-blue-500 bg-blue-500/10 rounded-full">🏠</button>
        <button class="p-3 text-gray-500">📊</button>
        <button class="p-3 text-gray-500">⚙️</button>
    </nav>
</div>

<script>
    const grid = document.getElementById("machineGrid");
    for(let i=1; i<=4; i++) {
        grid.innerHTML += `
        <div class="glass node-card rounded-[1.5rem] p-5 flex items-center gap-4">
            <img src="https://source.unsplash.com/100x100/?crypto,network&sig=${i}" class="w-16 h-16 rounded-2xl object-cover">
            <div class="flex-grow">
                <h4 class="font-bold">Node Machine ${i}</h4>
                <p class="text-[10px] text-blue-400">Profit: 50 PKR/day</p>
                <div class="w-full bg-white/10 h-1.5 rounded-full mt-2">
                    <div class="bg-blue-500 h-1.5 rounded-full w-[60%]"></div>
                </div>
            </div>
            <button class="bg-blue-600 p-3 rounded-2xl font-bold text-xs">BUY</button>
        </div>`;
    }

    // Live Mining
    setInterval(() => {
        let b = parseFloat(document.getElementById("balance").innerText);
        document.getElementById("balance").innerText = (b + 0.0005).toFixed(6);
    }, 1000);

    // Secret Admin
    let t=0; document.getElementById("adminLogo").onclick = () => {
        t++; if(t>=5 && prompt("Access Key:")=="5426") alert("System Overridden");
    };
</script>
</body>
</html>
