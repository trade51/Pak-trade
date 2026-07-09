<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trade 1 | Unified System</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-900 text-white font-sans p-4">

    <!-- Header -->
    <header class="flex justify-between items-center mb-8 border-b border-gray-700 pb-4">
        <div id="adminLogo" class="cursor-pointer">
            <h1 class="text-2xl font-bold text-blue-500">Trade 1</h1>
        </div>
        <div id="userHeader" class="text-right">
            <p class="text-xs text-gray-400">Balance</p>
            <h2 id="balance" class="text-xl font-bold">0.00 PKR</h2>
        </div>
    </header>

    <!-- Main Content Container -->
    <div id="contentArea">
        
        <!-- USER VIEW -->
        <div id="userView">
            <div class="bg-gray-800 p-6 rounded-xl border border-green-500 mb-6">
                <h3 class="text-sm text-gray-400">Live Mining</h3>
                <p id="earningsDisplay" class="text-3xl font-bold text-green-400">0.000000 PKR</p>
            </div>
            
            <div class="bg-gray-800 p-6 rounded-xl border border-gray-700">
                <h3 class="font-bold mb-4">Investment Deposit</h3>
                <form id="depositForm" class="space-y-3">
                    <input type="text" id="tid" placeholder="TID Number" class="w-full bg-gray-900 p-2 rounded border border-gray-700" required>
                    <input type="number" id="amount" placeholder="Amount (Min 300)" class="w-full bg-gray-900 p-2 rounded border border-gray-700" required>
                    <button type="submit" class="w-full bg-blue-600 p-2 rounded font-bold hover:bg-blue-700">Submit</button>
                </form>
            </div>
        </div>

        <!-- ADMIN VIEW (Initially Hidden) -->
        <div id="adminView" class="hidden">
            <h2 class="text-red-500 font-bold mb-4">ADMIN CONTROL PANEL</h2>
            <div class="bg-gray-800 p-4 rounded border border-red-500 overflow-x-auto">
                <table class="w-full text-sm">
                    <thead><tr class="text-gray-400 border-b border-gray-700"><th class="p-2">User TID</th><th class="p-2">Action</th></tr></thead>
                    <tbody id="adminTable">
                        <tr class="border-b border-gray-700">
                            <td class="p-2">TID-998877</td>
                            <td class="p-2 space-x-1">
                                <button onclick="alert('Balance Updated!')" class="bg-green-600 px-2 py-1 rounded">Approve</button>
                                <button onclick="alert('Request Rejected!')" class="bg-red-600 px-2 py-1 rounded">Reject</button>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <button onclick="location.reload()" class="mt-4 w-full bg-gray-700 p-2 rounded">Exit Admin Mode</button>
        </div>

    </div>

    <script>
        // 1. Live Mining Simulation
        let earnings = 0;
        setInterval(() => {
            earnings += 0.0005;
            document.getElementById("earningsDisplay").innerText = earnings.toFixed(6) + " PKR";
        }, 1000);

        // 2. Admin Mode Trigger (5 Taps + Key)
        let tapCount = 0;
        document.getElementById("adminLogo").addEventListener("click", () => {
            tapCount++;
            if (tapCount >= 5) {
                const key = prompt("Enter Admin Key:");
                if (key === "5426") {
                    document.getElementById("userView").classList.add("hidden");
                    document.getElementById("userHeader").classList.add("hidden");
                    document.getElementById("adminView").classList.remove("hidden");
                }
                tapCount = 0;
            }
        });

        // 3. Deposit Submit
        document.getElementById("depositForm").addEventListener("submit", (e) => {
            e.preventDefault();
            alert("Deposit Request Submitted to Admin!");
        });
    </script>
</body>
</html>
