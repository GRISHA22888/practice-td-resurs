<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Отчёт по практике | ТД Ресурс | Апгрейд</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: #eef2f5;
            padding: 20px 24px;
            color: #1e2f3e;
            transition: background 0.3s, color 0.2s;
        }

        body.dark-mode {
            background: #1a252f;
            color: #e2e8f0;
        }

        body.dark-mode .card,
        body.dark-mode .company-box,
        body.dark-mode .tab-btn,
        body.dark-mode .stat-item,
        body.dark-mode .team-item {
            background: #2d3e4e;
            border-color: #4a627a;
            color: #e2e8f0;
        }

        body.dark-mode .editable-field {
            background: #3e5a6c;
            color: white;
        }

        .wrapper {
            max-width: 1600px;
            margin: 0 auto;
        }

        /* шапка */
        .company-box {
            background: white;
            border-radius: 20px;
            padding: 20px 28px;
            margin-bottom: 24px;
            border: 1px solid #dce5ed;
        }

        .company-box h1 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: #1a4a6e;
        }

        .company-box p {
            font-size: 0.7rem;
            color: #4a627a;
        }

        /* топ-панель с кнопками */
        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 24px;
        }

        .theme-btn {
            background: white;
            border: 1px solid #cbd5e1;
            padding: 8px 20px;
            border-radius: 40px;
            cursor: pointer;
            font-size: 0.75rem;
        }

        .tabs-row {
            display: flex;
            gap: 12px;
            margin-bottom: 28px;
            flex-wrap: wrap;
        }

        .tab-btn {
            background: white;
            border: 1px solid #cbd5e1;
            padding: 10px 26px;
            border-radius: 40px;
            cursor: pointer;
            font-size: 0.85rem;
            font-weight: 500;
        }

        .tab-btn.active {
            background: #1e5a7d;
            color: white;
            border-color: #1e5a7d;
        }

        .page {
            display: none;
        }

        .page.active {
            display: block;
        }

        .card {
            background: white;
            border-radius: 24px;
            padding: 24px 28px;
            margin-bottom: 24px;
            border: 1px solid #e2e8f0;
            box-shadow: 0 1px 3px rgba(0,0,0,0.04);
        }

        .card h2 {
            font-size: 1.3rem;
            margin-bottom: 18px;
            border-left: 4px solid #f5a623;
            padding-left: 16px;
        }

        .grid-2col {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 24px;
        }

        @media (max-width: 800px) {
            .grid-2col { grid-template-columns: 1fr; }
        }

        .json-block {
            background: #0f172a;
            color: #cbd5e6;
            font-family: monospace;
            font-size: 0.7rem;
            padding: 14px;
            border-radius: 14px;
            overflow-x: auto;
        }

        body.dark-mode .json-block {
            background: #1e2a3a;
        }

        .tag {
            background: #eef2ff;
            padding: 3px 12px;
            border-radius: 30px;
            font-size: 0.7rem;
            display: inline-block;
            margin: 4px 6px 4px 0;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.85rem;
        }

        th {
            text-align: left;
            padding: 12px 8px;
            background: #f1f5f9;
            border-bottom: 1px solid #e2e8f0;
            cursor: pointer;
        }

        body.dark-mode th {
            background: #3e5a6c;
        }

        td {
            padding: 10px 8px;
            border-bottom: 1px solid #edf2f7;
        }

        .editable-field {
            background: #fffef5;
            padding: 4px 10px;
            border-radius: 20px;
            display: inline-block;
            cursor: text;
            border: 1px solid #e2dcc8;
            min-width: 70px;
        }

        .editable-field.highlight-search {
            background: #fde047;
            box-shadow: 0 0 0 2px #f5a623;
        }

        .drag-handle {
            cursor: grab;
            text-align: center;
            color: #8899bb;
            user-select: none;
        }

        .toolbar {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            justify-content: space-between;
            margin-bottom: 20px;
        }

        .btn {
            background: #edf2f7;
            border: none;
            padding: 6px 16px;
            border-radius: 30px;
            font-size: 0.75rem;
            cursor: pointer;
        }

        .btn-primary {
            background: #1e5a7d;
            color: white;
        }

        .filter-input {
            padding: 6px 14px;
            border-radius: 30px;
            border: 1px solid #cbd5e1;
            font-size: 0.75rem;
        }

        .total-big {
            text-align: right;
            font-weight: 700;
            font-size: 1.1rem;
            margin-top: 16px;
            padding-top: 14px;
            border-top: 2px solid #e2e8f0;
        }

        .stat-row {
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
            margin: 12px 0;
        }

        .stat-item {
            background: #f8fafc;
            padding: 6px 14px;
            border-radius: 30px;
            font-size: 0.75rem;
        }

        .history-list {
            max-height: 180px;
            overflow-y: auto;
            background: #fefce8;
            padding: 10px;
            border-radius: 16px;
            font-size: 0.7rem;
        }

        .context-menu {
            position: fixed;
            background: white;
            border: 1px solid #cbd5e1;
            border-radius: 12px;
            padding: 6px 0;
            z-index: 2000;
            display: none;
            min-width: 150px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .context-menu div {
            padding: 8px 18px;
            cursor: pointer;
            font-size: 0.75rem;
        }

        .context-menu div:hover {
            background: #eef2f5;
        }

        .chart-container {
            height: 200px;
            margin: 12px 0;
        }

        canvas {
            max-width: 100%;
            background: white;
            border-radius: 16px;
            padding: 8px;
        }

        .toast-msg {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #2c3e4e;
            color: white;
            padding: 8px 18px;
            border-radius: 40px;
            font-size: 0.7rem;
            opacity: 0;
            transition: 0.2s;
            z-index: 1000;
        }

        footer {
            margin-top: 40px;
            text-align: center;
            font-size: 0.7rem;
            color: #6c7a8e;
        }

        .code-sample {
            background: #f1f3f5;
            padding: 12px;
            border-radius: 14px;
            font-family: monospace;
            font-size: 0.7rem;
            margin: 10px 0;
        }
    </style>
</head>
<body>
<div class="wrapper">
    <div class="company-box">
        <h1>ООО «Торговый дом Ресурс»</h1>
        <p>Полное: Общество с ограниченной ответственностью «Торговый дом Ресурс» | Сокращённо: ООО «Т.Д. Ресурс»<br>
        Юр.адрес: 624691, Свердловская обл., Алапаевский р-н, р.п. Верхняя Синячиха, Октябрьская ул., 21-7<br>
        Факт.адрес: ст. Синячиха, ул. Вокзальная, д.15</p>
    </div>

    <div class="top-bar">
        <div class="tabs-row" style="margin-bottom: 0;">
            <div class="tab-btn active" data-page="practice">1. Практика и команда</div>
            <div class="tab-btn" data-page="datamodel">2. Модель данных / JSON</div>
            <div class="tab-btn" data-page="frontend">3. Фронтенд (апгрейд версия)</div>
        </div>
        <button id="themeToggleBtn" class="theme-btn">🌙 Ночной режим</button>
    </div>

    <!-- СТРАНИЦА 1: ПРАКТИКА (живой текст) -->
    <div id="practicePage" class="page active">
        <div class="card">
            <h2>Что я делал на практике</h2>
            <p style="margin-bottom: 12px;">Пришёл в ИТ-отдел ТД Ресурс в начале апреля. Компания торгует металлопрокатом — трубы, листы, швеллеры. Их внутренняя система для отгрузок была старой и тормознутой, особенно таблица с товарами загружалась по 3-4 секунды. Мне сказали: Переделай фронтенд , чтобы можно было редактировать прямо в таблице и быстрее работало.</p>
            <p style="margin-bottom: 12px;">Первые дни просто смотрел, какие запросы летят, что приходит с бэка. Лёша (бэкенд) показал все API. Потом начал кодить. Сделал таблицу на JS. Реализовал редактирование через contenteditable, пересчёт суммы на лету, фильтр, сортировку, историю изменений (undo/redo). Потом добавил drag&drop для сортировки строк, контекстное меню (ПКМ), экспорт в CSV и Excel, график цен и ночной режим.</p>
            <p>В итоге страница стала грузиться где-то на 40% быстрее. Руководитель сказал: норм, выкатывай в тест. Сейчас уже три менеджера склада пользуются, не жалуются.</p>
        </div>

        <div class="card">
            <h2>Команда и как подружились</h2>
            <div style="display: flex; flex-direction: column; gap: 14px;">
                <div class="team-item" style="padding: 12px; background: #f8fafc; border-radius: 16px;">
                    <strong>Сергей Михайлович</strong>  руководитель. Доверил мне правки в тестовый контур уже на второй неделе. Говорит: «У тебя глаз намётанный».
                </div>
                <div class="team-item" style="padding: 12px; background: #f8fafc; border-radius: 16px;">
                    <strong>Лёша (бэкенд)</strong>  Вместе ходили в столовку, он научил меня правильно писать запросы и объяснил, почему у них поля называются странно.
                </div>
                <div class="team-item" style="padding: 12px; background: #f8fafc; border-radius: 16px;">
                    <strong>Настя (QA)</strong> Находила баги и кидала в чат. Она научила меня писать понятные баг-репорты.
                </div>
                <div class="team-item" style="padding: 12px; background: #f8fafc; border-radius: 16px;">
                    <strong>Дима (аналитик)</strong> он сказал: «Сделай минимально работающее, потом доделаешь». Правильный совет.
                </div>
            </div>
        </div>
    </div>

    <!-- СТРАНИЦА 2: МОДЕЛЬ ДАННЫХ -->
    <div id="datamodelPage" class="page">
        <div class="card">
            <h2>Что прилетает с бэка (GET)</h2>
            <div class="json-block" id="incomingModelJson">{"docId":10234,"date":"2026-05-04","items":[]}</div>
        </div>
        <div class="card">
            <h2>Что улетает обратно (POST)</h2>
            <div class="json-block" id="outgoingModelJson">{}</div>
        </div>
        <div class="card">
            <h2>HTML-теги и атрибуты</h2>
            <div><span class="tag">&lt;table&gt;</span><span class="tag">contenteditable</span><span class="tag">data-idx</span><span class="tag">data-field</span><span class="tag">dragstart/drop</span><span class="tag">contextmenu</span></div>
            <div class="code-sample">
                &lt;tr draggable="true" data-rowid="1"&gt;<br>
                &nbsp;&nbsp;&lt;td class="drag-handle"&gt;⠿&lt;/td&gt;<br>
                &nbsp;&nbsp;&lt;td&gt;&lt;span contenteditable="true" data-field="qty"&gt;12&lt;/span&gt;&lt;/td&gt;<br>
                &lt;/tr&gt;
            </div>
        </div>
    </div>

    <!-- СТРАНИЦА 3: ФРОНТЕНД МАКСИМАЛЬНЫЙ АПГРЕЙД -->
    <div id="frontendPage" class="page">
        <div class="card">
            <div class="toolbar">
                <div>
                    <button id="undoFrontBtn" class="btn">↩ Отменить (Ctrl+Z)</button>
                    <button id="redoFrontBtn" class="btn">↪ Повторить (Ctrl+Y)</button>
                    <button id="exportJsonBtn" class="btn">📋 JSON</button>
                    <button id="exportCsvBtn" class="btn">📄 CSV</button>
                    <button id="exportExcelBtn" class="btn">📊 Excel (XLS)</button>
                    <button id="importJsonBtn" class="btn">📂 Импорт JSON</button>
                    <button id="addRowBtn" class="btn">➕ Новая строка</button>
                </div>
                <div>
                    <input type="text" id="searchHighlightInput" class="filter-input" placeholder="🔍 Поиск с подсветкой...">
                    <input type="text" id="filterInputFront" class="filter-input" placeholder="Фильтр по названию..." style="margin-left: 6px;">
                </div>
            </div>
            <h2>Таблица отгрузок (drag&drop, ПКМ, редактирование)</h2>
            <div style="overflow-x: auto;">
                <table id="mainFrontTable">
                    <thead>
                        <tr><th style="width: 30px;"></th><th data-sort="name">Товар</th><th data-sort="qty">Кол-во</th><th data-sort="price">Цена</th><th>Сумма</th><th></th></tr>
                    </thead>
                    <tbody id="frontTableBody"></tbody>
                </table>
            </div>
            <div class="total-big" id="totalSumFront">Общая стоимость: 0 руб.</div>
            <div style="display: flex; justify-content: flex-end; gap: 12px; margin-top: 18px;">
                <button id="resetFrontBtn" class="btn">Сбросить всё</button>
                <button id="submitFrontBtn" class="btn-primary">Отправить на сервер (POST)</button>
            </div>
        </div>

        <div class="grid-2col">
            <div class="card">
                <h2>Статистика</h2>
                <div class="stat-row"><div class="stat-item">📦 Позиций: <span id="statCount">0</span></div><div class="stat-item">🔄 Изменено: <span id="statChanged">нет</span></div><div class="stat-item">💰 Средняя цена: <span id="statAvg">0</span></div></div>
                <div class="stat-row"><div class="stat-item">📊 Макс. кол-во: <span id="statMaxQty">0</span></div><div class="stat-item">💸 Макс. цена: <span id="statMaxPrice">0</span></div><div class="stat-item">📈 Сумма: <span id="statTotal">0</span></div></div>
            </div>
            <div class="card">
                <h2>История действий (undo/redo)</h2>
                <div class="history-list" id="historyList">— пока пусто —</div>
            </div>
        </div>

        <div class="card">
            <h2>График цен на товары</h2>
            <div class="chart-container">
                <canvas id="priceChart" width="600" height="180" style="width:100%; height:180px; background:#fff; border-radius:16px;"></canvas>
            </div>
        </div>

        <div class="card">
            <h2>Что улетит на сервер (актуальный JSON)</h2>
            <div class="json-block" id="liveOutgoingJson"></div>
        </div>

        <div class="card">
            <h2>Что я добавил в апгрейде (список фич)</h2>
            <ul style="margin-left: 20px;">
                <li>✅ Перетаскивание строк (drag & drop) — меняйте порядок товаров</li>
                <li>✅ Контекстное меню (ПКМ на строке) — дублировать, удалить, редактировать</li>
                <li>✅ Ночной режим (кнопка в шапке) — не слепит глаза</li>
                <li>✅ Экспорт в CSV и Excel (XLS через data:application)</li>
                <li>✅ Импорт из JSON (загрузить любой документ)</li>
                <li>✅ Поиск с подсветкой ячеек</li>
                <li>✅ График цен на товары (CanvasJS + Chart.js своими руками)</li>
                <li>✅ Кнопка добавления новой строки</li>
                <li>✅ Горячие клавиши Ctrl+Z / Ctrl+Y</li>
                <li>✅ Подсветка изменённых полей (жёлтым)</li>
            </ul>
        </div>
    </div>

    <footer>Практика ООО «ТД Ресурс»</footer>
</div>
<div id="toastGlobal" class="toast-msg"></div>
<div id="contextMenu" class="context-menu">
    <div id="cmEdit">✏️ Редактировать</div>
    <div id="cmDuplicate">📄 Дублировать строку</div>
    <div id="cmDelete">🗑 Удалить строку</div>
</div>

<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>
<script>
    // ---------- ДАННЫЕ ----------
    let storeItems = [
        { id: 1, name: "Труба ВГП 25х3.2", qty: 12, price: 450 },
        { id: 2, name: "Лист стальной 3мм", qty: 5, price: 1200 },
        { id: 3, name: "Уголок 50х50х4", qty: 8, price: 620 },
        { id: 4, name: "Швеллер 10П", qty: 3, price: 1430 },
        { id: 5, name: "Балка двутавр 12", qty: 2, price: 2560 }
    ];
    let originalStore = JSON.parse(JSON.stringify(storeItems));
    let historyStore = [JSON.parse(JSON.stringify(storeItems))];
    let historyIndex = 0;
    let filterText = "";
    let searchText = "";
    let chartInstance = null;

    function pushHistory() {
        historyStore = historyStore.slice(0, historyIndex + 1);
        historyStore.push(JSON.parse(JSON.stringify(storeItems)));
        historyIndex++;
        updateHistoryDisplay();
    }

    function undo() { if (historyIndex > 0) { historyIndex--; storeItems = JSON.parse(JSON.stringify(historyStore[historyIndex])); renderTable(); updateStatsAndJson(); showToast("Отменил"); } else showToast("Нечего отменять"); }
    function redo() { if (historyIndex < historyStore.length - 1) { historyIndex++; storeItems = JSON.parse(JSON.stringify(historyStore[historyIndex])); renderTable(); updateStatsAndJson(); showToast("Повторил"); } else showToast("Нечего повторять"); }

    let draggedRow = null;
    function handleDragStart(e, idx) { draggedRow = idx; e.dataTransfer.effectAllowed = "move"; }
    function handleDragOver(e) { e.preventDefault(); e.dataTransfer.dropEffect = "move"; }
    function handleDrop(e, targetIdx) { e.preventDefault(); if (draggedRow !== null && draggedRow !== targetIdx) { const moved = storeItems[draggedRow]; storeItems.splice(draggedRow, 1); storeItems.splice(targetIdx, 0, moved); pushHistory(); renderTable(); showToast("Порядок строк изменён"); } draggedRow = null; }

    let contextRowIndex = null;
    function openContextMenu(e, idx) { e.preventDefault(); contextRowIndex = idx; let menu = document.getElementById("contextMenu"); menu.style.display = "block"; menu.style.left = e.pageX + "px"; menu.style.top = e.pageY + "px"; }
    function closeMenu() { document.getElementById("contextMenu").style.display = "none"; contextRowIndex = null; }
    document.getElementById("cmDuplicate")?.addEventListener("click", () => { if (contextRowIndex !== null) { const cloned = JSON.parse(JSON.stringify(storeItems[contextRowIndex])); cloned.id = Date.now(); storeItems.splice(contextRowIndex + 1, 0, cloned); pushHistory(); renderTable(); closeMenu(); showToast("Дублировал строку"); } });
    document.getElementById("cmDelete")?.addEventListener("click", () => { if (contextRowIndex !== null) { storeItems.splice(contextRowIndex, 1); pushHistory(); renderTable(); closeMenu(); showToast("Удалил"); } });
    document.getElementById("cmEdit")?.addEventListener("click", () => { closeMenu(); showToast("Кликните по ячейке для правки"); });
    document.addEventListener("click", () => closeMenu());

    function renderTable() {
        let filtered = storeItems.filter(i => i.name.toLowerCase().includes(filterText.toLowerCase()));
        let tbody = document.getElementById("frontTableBody");
        if (!tbody) return;
        tbody.innerHTML = "";
        filtered.forEach((item, idx) => {
            let realIdx = storeItems.findIndex(i => i.id === item.id);
            let row = tbody.insertRow();
            row.draggable = true;
            row.setAttribute("data-idx", realIdx);
            row.ondragstart = (e) => handleDragStart(e, realIdx);
            row.ondragover = handleDragOver;
            row.ondrop = (e) => handleDrop(e, realIdx);
            row.oncontextmenu = (e) => openContextMenu(e, realIdx);

            let dragCell = row.insertCell(0);
            dragCell.className = "drag-handle";
            dragCell.innerText = "⠿";

            let nameCell = row.insertCell(1);
            nameCell.innerText = item.name;
            if (searchText && item.name.toLowerCase().includes(searchText.toLowerCase())) nameCell.style.backgroundColor = "#fde047";

            let qtyCell = row.insertCell(2);
            let qtySpan = document.createElement("span");
            qtySpan.className = "editable-field";
            qtySpan.setAttribute("contenteditable", "true");
            qtySpan.setAttribute("data-field", "qty");
            qtySpan.setAttribute("data-idx", realIdx);
            qtySpan.innerText = item.qty;
            if (originalStore[realIdx] && originalStore[realIdx].qty !== item.qty) qtySpan.style.background = "#fff0c0";
            if (searchText && item.qty.toString().includes(searchText)) qtySpan.style.background = "#fde047";
            qtyCell.appendChild(qtySpan);

            let priceCell = row.insertCell(3);
            let priceSpan = document.createElement("span");
            priceSpan.className = "editable-field";
            priceSpan.setAttribute("contenteditable", "true");
            priceSpan.setAttribute("data-field", "price");
            priceSpan.setAttribute("data-idx", realIdx);
            priceSpan.innerText = item.price.toFixed(2);
            if (originalStore[realIdx] && originalStore[realIdx].price !== item.price) priceSpan.style.background = "#fff0c0";
            if (searchText && item.price.toString().includes(searchText)) priceSpan.style.background = "#fde047";
            priceCell.appendChild(priceSpan);

            let sumCell = row.insertCell(4);
            sumCell.innerText = (item.qty * item.price).toFixed(2) + " руб.";

            let delCell = row.insertCell(5);
            let delBtn = document.createElement("button");
            delBtn.innerText = "✕";
            delBtn.style.background = "#fde5e5";
            delBtn.style.padding = "4px 10px";
            delBtn.onclick = () => { if (confirm("Удалить?")) { storeItems.splice(realIdx, 1); pushHistory(); renderTable(); updateStatsAndJson(); showToast("Удалено"); } };
            delCell.appendChild(delBtn);
        });
        attachEditEvents();
        updateStatsAndJson();
        drawChart();
    }

    function attachEditEvents() {
        document.querySelectorAll("#frontTableBody .editable-field").forEach(el => {
            el.removeEventListener("blur", editHandler);
            el.addEventListener("blur", editHandler);
        });
    }

    function editHandler(e) {
        let span = e.target;
        let field = span.getAttribute("data-field");
        let idx = parseInt(span.getAttribute("data-idx"));
        if (isNaN(idx)) return;
        let raw = span.innerText.trim();
        let newVal = field === "qty" ? parseInt(raw) : parseFloat(raw);
        if (isNaN(newVal) || newVal < 0) newVal = storeItems[idx][field];
        if (storeItems[idx][field] === newVal) return;
        storeItems[idx][field] = newVal;
        pushHistory();
        renderTable();
        showToast(`${field} → ${newVal}`);
    }

    function addNewRow() { let newId = Date.now(); storeItems.push({ id: newId, name: "Новый товар", qty: 1, price: 100 }); pushHistory(); renderTable(); showToast("Добавлена новая строка"); }

    function updateStatsAndJson() {
        let total = storeItems.reduce((s, i) => s + i.qty * i.price, 0);
        document.getElementById("totalSumFront").innerHTML = "Общая стоимость: " + total.toFixed(2) + " руб.";
        document.getElementById("statCount").innerText = storeItems.length;
        let changed = JSON.stringify(storeItems) !== JSON.stringify(originalStore);
        document.getElementById("statChanged").innerHTML = changed ? "да" : "нет";
        let avg = storeItems.length ? (total / storeItems.length).toFixed(2) : 0;
        document.getElementById("statAvg").innerHTML = avg;
        document.getElementById("statMaxQty").innerHTML = storeItems.length ? Math.max(...storeItems.map(i => i.qty)) : 0;
        document.getElementById("statMaxPrice").innerHTML = storeItems.length ? Math.max(...storeItems.map(i => i.price)) : 0;
        document.getElementById("statTotal").innerHTML = total.toFixed(2);

        let outgoing = { docId: 10234, isModified: changed, items: storeItems, timestamp: new Date().toISOString() };
        document.getElementById("liveOutgoingJson").innerHTML = JSON.stringify(outgoing, null, 2);
        document.getElementById("incomingModelJson").innerHTML = JSON.stringify({ docId: 10234, date: "2026-05-04", items: storeItems }, null, 2);
        document.getElementById("outgoingModelJson").innerHTML = JSON.stringify(outgoing, null, 2);
    }

    function resetAll() { storeItems = JSON.parse(JSON.stringify(originalStore)); pushHistory(); renderTable(); showToast("Сброшено"); }
    function submitAll() { showToast("Отправлено на сервер. Позиций: " + storeItems.length); originalStore = JSON.parse(JSON.stringify(storeItems)); renderTable(); }

    function exportCSV() { let csv = "Name,Qty,Price,Sum\n" + storeItems.map(i => `${i.name},${i.qty},${i.price},${i.qty*i.price}`).join("\n"); let blob = new Blob([csv], {type: "text/csv"}); let a = document.createElement("a"); a.href = URL.createObjectURL(blob); a.download = "tdresurs_export.csv"; a.click(); showToast("CSV скачан"); }
    function exportExcel() { let html = `<table><tr><th>Name</th><th>Qty</th><th>Price</th><th>Sum</th></tr>${storeItems.map(i => `<tr><td>${i.name}</td><td>${i.qty}</td><td>${i.price}</td><td>${i.qty*i.price}</td></tr>`).join("")}</table>`; let blob = new Blob([html], {type: "application/vnd.ms-excel"}); let a = document.createElement("a"); a.href = URL.createObjectURL(blob); a.download = "tdresurs_export.xls"; a.click(); showToast("Excel скачан"); }
    function exportJSON() { navigator.clipboard.writeText(JSON.stringify({ doc: storeItems }, null, 2)); showToast("JSON скопирован"); }
    function importJSON() { let txt = prompt("Вставьте JSON (массив items или документ)"); if (!txt) return; try { let parsed = JSON.parse(txt); let items = parsed.items || (Array.isArray(parsed) ? parsed : null); if (items && items.length) { storeItems = items.map((it, idx) => ({ id: idx + 1, name: it.name, qty: it.qty, price: it.price })); originalStore = JSON.parse(JSON.stringify(storeItems)); pushHistory(); renderTable(); showToast("Импорт готов"); } else throw new Error(); } catch(e) { showToast("Ошибка формата JSON"); } }

    function sortTable(field) { if (field === "name") storeItems.sort((a,b) => a.name.localeCompare(b.name)); else if (field === "qty") storeItems.sort((a,b) => a.qty - b.qty); else if (field === "price") storeItems.sort((a,b) => a.price - b.price); pushHistory(); renderTable(); showToast(`Сортировка по ${field}`); }

    function drawChart() { let canvas = document.getElementById("priceChart"); if (!canvas || !storeItems.length) return; let ctx = canvas.getContext("2d"); if (chartInstance) chartInstance.destroy(); chartInstance = new Chart(ctx, { type: "bar", data: { labels: storeItems.map(i => i.name.length > 15 ? i.name.slice(0,12)+"..." : i.name), datasets: [{ label: "Цена (руб)", data: storeItems.map(i => i.price), backgroundColor: "#f5a623", borderRadius: 8 }] }, options: { responsive: true, maintainAspectRatio: true, plugins: { legend: { position: "top" } } } }); }

    function updateHistoryDisplay() { let cont = document.getElementById("historyList"); if (!cont) return; cont.innerHTML = historyStore.map((_, i) => `<div style="padding: 2px 0; ${i === historyIndex ? "background:#fef3c7; padding-left:6px;" : ""}">📌 Шаг ${i} ${i === historyIndex ? "← текущий" : ""}</div>`).join(""); }

    function showToast(msg) { let t = document.getElementById("toastGlobal"); t.innerText = msg; t.style.opacity = "1"; setTimeout(() => t.style.opacity = "0", 1500); }

    // тема
    function toggleTheme() { document.body.classList.toggle("dark-mode"); localStorage.setItem("theme", document.body.classList.contains("dark-mode") ? "dark" : "light"); }
    if (localStorage.getItem("theme") === "dark") document.body.classList.add("dark-mode");

    // переключение страниц
    function switchPage(pageId) { document.querySelectorAll(".page").forEach(p => p.classList.remove("active")); document.getElementById(pageId + "Page").classList.add("active"); document.querySelectorAll(".tab-btn").forEach(btn => btn.classList.remove("active")); document.querySelector(`.tab-btn[data-page="${pageId}"]`).classList.add("active"); if (pageId === "frontend") { renderTable(); drawChart(); } }

    document.addEventListener("DOMContentLoaded", () => {
        renderTable(); pushHistory();
        document.getElementById("undoFrontBtn")?.addEventListener("click", undo); document.getElementById("redoFrontBtn")?.addEventListener("click", redo);
        document.getElementById("resetFrontBtn")?.addEventListener("click", resetAll); document.getElementById("submitFrontBtn")?.addEventListener("click", submitAll);
        document.getElementById("exportJsonBtn")?.addEventListener("click", exportJSON); document.getElementById("exportCsvBtn")?.addEventListener("click", exportCSV);
        document.getElementById("exportExcelBtn")?.addEventListener("click", exportExcel); document.getElementById("importJsonBtn")?.addEventListener("click", importJSON);
        document.getElementById("addRowBtn")?.addEventListener("click", addNewRow);
        document.getElementById("filterInputFront")?.addEventListener("input", (e) => { filterText = e.target.value; renderTable(); });
        document.getElementById("searchHighlightInput")?.addEventListener("input", (e) => { searchText = e.target.value; renderTable(); });
        document.querySelectorAll("#mainFrontTable th[data-sort]").forEach(th => th.addEventListener("click", () => sortTable(th.getAttribute("data-sort"))));
        document.querySelectorAll(".tab-btn").forEach(btn => btn.addEventListener("click", () => switchPage(btn.getAttribute("data-page"))));
        document.getElementById("themeToggleBtn")?.addEventListener("click", toggleTheme);
        document.addEventListener("keydown", (e) => { if (e.ctrlKey && e.key === "z") { e.preventDefault(); undo(); } if (e.ctrlKey && e.key === "y") { e.preventDefault(); redo(); } });
    });
</script>
</body>
</html>
