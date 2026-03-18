<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GX Sync Pro | Universal Auto-Sync</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    
    <style>
        :root { --primary: #3b82f6; --bg: #030712; --card: rgba(17, 24, 39, 0.8); }
        body {
            background-color: var(--bg);
            color: #f3f4f6;
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-image: radial-gradient(circle at 50% -20%, #1e293b 0%, #030712 100%);
            min-height: 100vh;
        }
        .premium-glass {
            background: var(--card);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.05);
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
        }
        .custom-input, .code-area {
            background: rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }
        .custom-input:focus, .code-area:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 15px rgba(59, 130, 246, 0.2);
        }
        .list-card { transition: all 0.3s ease; border-left-width: 4px; }
        .list-card:hover { transform: scale(1.01); background: rgba(255, 255, 255, 0.05); }
        ::-webkit-scrollbar { width: 5px; }
        ::-webkit-scrollbar-thumb { background: #374151; border-radius: 10px; }
    </style>
</head>
<body class="p-4 md:p-10">

    <div class="max-w-6xl mx-auto">
        <header class="mb-10 flex flex-col md:flex-row justify-between items-center gap-4">
            <div>
                <h1 class="text-3xl font-black italic text-white uppercase tracking-tighter">GX<span class="text-blue-500 text-4xl">.</span>SYNC</h1>
                <p class="text-gray-500 text-[10px] uppercase font-bold tracking-[3px]">Universal Database System</p>
            </div>
            <div class="flex items-center gap-3">
                <span id="counter" class="bg-blue-600/20 text-blue-400 px-4 py-1 rounded-full text-xs font-bold border border-blue-500/20">0 ITEMS</span>
            </div>
        </header>

        <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
            
            <div class="lg:col-span-5 space-y-6">
                <div class="premium-glass p-8 rounded-[2.5rem]">
                    <h2 class="text-sm font-black text-gray-400 uppercase tracking-widest mb-6">Manage Entry</h2>
                    <div class="space-y-4">
                        <div class="space-y-1">
                            <label class="text-[10px] text-gray-500 ml-2 font-bold uppercase">Title</label>
                            <input type="text" id="title" placeholder="e.g. My Project" class="custom-input w-full p-4 rounded-2xl text-sm">
                        </div>
                        <div class="space-y-1">
                            <label class="text-[10px] text-gray-500 ml-2 font-bold uppercase">Link / URL</label>
                            <input type="text" id="link" placeholder="https://..." class="custom-input w-full p-4 rounded-2xl text-sm">
                        </div>
                        <div class="grid grid-cols-2 gap-4">
                            <div class="space-y-1">
                                <label class="text-[10px] text-gray-500 ml-2 font-bold uppercase">Type</label>
                                <select id="cat" class="custom-input w-full p-4 rounded-2xl text-sm cursor-pointer text-white">
                                    <option value="app">🚀 App</option>
                                    <option value="file">📁 File</option>
                                    <option value="web">🌐 Web</option>
                                </select>
                            </div>
                            <div class="space-y-1">
                                <label class="text-[10px] text-gray-500 ml-2 font-bold uppercase">Color</label>
                                <input type="color" id="color" value="#3b82f6" class="w-full h-[54px] bg-transparent border-none cursor-pointer">
                            </div>
                        </div>
                        
                        <input type="hidden" id="edit-index" value="-1">
                        
                        <button onclick="handleSave()" id="save-btn" class="w-full mt-4 py-4 bg-white text-black font-black uppercase tracking-widest rounded-2xl hover:bg-blue-600 hover:text-white transition-all duration-300 shadow-lg active:scale-95">
                            Save & Clear
                        </button>
                    </div>
                </div>

                <div class="premium-glass p-6 rounded-[2.5rem]">
                    <div class="flex justify-between items-center mb-4 px-2">
                        <span class="text-[10px] font-bold text-gray-500 tracking-widest uppercase">Sync Code Area</span>
                        <button onclick="copyCode()" id="copy-btn" class="text-[10px] bg-blue-500 text-white px-3 py-1 rounded-lg font-bold">COPY CODE</button>
                    </div>
                    <textarea id="json-box" class="code-area w-full h-48 p-5 rounded-2xl font-mono text-[11px] text-blue-400 leading-relaxed" placeholder="Paste any JSON code here..."></textarea>
                </div>
            </div>

            <div class="lg:col-span-7">
                <div id="list-container" class="space-y-4 max-h-[85vh] overflow-y-auto pr-2">
                </div>
            </div>

        </div>
    </div>

    <script>
        let dataStore = JSON.parse(localStorage.getItem('GX_PRO_DB')) || [];
        const jsonBox = document.getElementById('json-box');

        window.onload = () => renderUI(true);

        function handleSave() {
            const titleInput = document.getElementById('title');
            const linkInput = document.getElementById('link');
            const cat = document.getElementById('cat').value;
            const color = document.getElementById('color').value;
            const editIndex = document.getElementById('edit-index').value;

            if (!titleInput.value || !linkInput.value) return alert("Title and Link are required!");

            const item = { title: titleInput.value.trim(), link: linkInput.value.trim(), cat, color };

            if (editIndex === "-1") {
                dataStore.unshift(item);
            } else {
                dataStore[editIndex] = item;
                resetForm();
            }

            saveData();
            titleInput.value = '';
            linkInput.value = '';
        }

        function renderUI(updateBox = false) {
            const listContainer = document.getElementById('list-container');
            listContainer.innerHTML = '';
            document.getElementById('counter').innerText = `${dataStore.length} ITEMS`;

            if (dataStore.length === 0) {
                listContainer.innerHTML = `<div class="p-10 text-center text-gray-600 italic">No data found. Paste JSON or add new.</div>`;
            }

            dataStore.forEach((item, index) => {
                // স্মার্ট ডিটেকশন: যেকোনো কী (Key) সাপোর্ট করবে
                const title = item.title || item.name || item.text || "Untitled";
                const link = item.link || item.url || item.href || "#";
                const color = item.color || "#3b82f6";
                const cat = item.cat || "item";

                listContainer.innerHTML += `
                    <div class="list-card premium-glass p-6 rounded-[2rem] flex items-center justify-between gap-4 border-l-4" style="border-left-color: ${color}">
                        <div class="flex-1 min-w-0">
                            <span class="text-[9px] font-black uppercase text-blue-500 bg-blue-500/10 px-2 py-0.5 rounded border border-blue-500/10">${cat}</span>
                            <h3 class="text-lg font-bold text-white truncate mt-1">${title}</h3>
                            <p class="text-[10px] text-gray-500 truncate font-mono mt-1">${link}</p>
                        </div>
                        <div class="flex gap-2">
                            <button onclick="editItem(${index})" class="p-3 bg-white/5 hover:bg-yellow-500/20 hover:text-yellow-500 rounded-xl transition-all border border-white/5">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M15.232 5.232l3.536 3.536m-2.036-5.036a2.5 2.5 0 113.536 3.536L6.5 21.036H3v-3.572L16.732 3.732z" stroke-width="2" stroke-linecap="round"></path></svg>
                            </button>
                            <button onclick="deleteItem(${index})" class="p-3 bg-white/5 hover:bg-red-500/20 hover:text-red-500 rounded-xl transition-all border border-white/5">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" stroke-width="2" stroke-linecap="round"></path></svg>
                            </button>
                        </div>
                    </div>`;
            });

            if (updateBox) jsonBox.value = JSON.stringify(dataStore, null, 2);
        }

        // অটো-ম্যাজিক সিঙ্ক: যেকোনো ফরম্যাটকে নিজের ফরম্যাটে কনভার্ট করবে
        jsonBox.addEventListener('input', () => {
            try {
                const parsed = JSON.parse(jsonBox.value);
                if (Array.isArray(parsed)) {
                    dataStore = parsed;
                    localStorage.setItem('GX_PRO_DB', JSON.stringify(dataStore));
                    renderUI(false);
                }
            } catch (e) {}
        });

        function deleteItem(index) {
            if (confirm("Delete permanently?")) {
                dataStore.splice(index, 1);
                saveData();
            }
        }

        function editItem(index) {
            const item = dataStore[index];
            document.getElementById('title').value = item.title || item.name || '';
            document.getElementById('link').value = item.link || item.url || '';
            document.getElementById('cat').value = item.cat || 'app';
            document.getElementById('color').value = item.color || '#3b82f6';
            document.getElementById('edit-index').value = index;
            const btn = document.getElementById('save-btn');
            btn.innerText = "Update Now";
            btn.style.background = "#eab308";
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        function resetForm() {
            document.getElementById('edit-index').value = "-1";
            document.getElementById('save-btn').innerText = "Save & Clear";
            document.getElementById('save-btn').style.background = "white";
        }

        function saveData() {
            localStorage.setItem('GX_PRO_DB', JSON.stringify(dataStore));
            renderUI(true);
        }

        function copyCode() {
            jsonBox.select();
            document.execCommand('copy');
            document.getElementById('copy-btn').innerText = "COPIED! ✅";
            setTimeout(() => document.getElementById('copy-btn').innerText = "COPY CODE", 2000);
        }
    </script>
</body>
</html>
