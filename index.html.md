<!DOCTYPE html>

<html lang="ru">

<head>

&#x20;   <meta charset="UTF-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1.0">

&#x20;   <title>Отчёт по практике | ТД Ресурс | Апгрейд</title>

&#x20;   <style>

&#x20;       \* {

&#x20;           margin: 0;

&#x20;           padding: 0;

&#x20;           box-sizing: border-box;

&#x20;       }



&#x20;       body {

&#x20;           font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;

&#x20;           background: #eef2f5;

&#x20;           padding: 20px 24px;

&#x20;           color: #1e2f3e;

&#x20;           transition: background 0.3s, color 0.2s;

&#x20;       }



&#x20;       body.dark-mode {

&#x20;           background: #1a252f;

&#x20;           color: #e2e8f0;

&#x20;       }



&#x20;       body.dark-mode .card,

&#x20;       body.dark-mode .company-box,

&#x20;       body.dark-mode .tab-btn,

&#x20;       body.dark-mode .stat-item,

&#x20;       body.dark-mode .team-item {

&#x20;           background: #2d3e4e;

&#x20;           border-color: #4a627a;

&#x20;           color: #e2e8f0;

&#x20;       }



&#x20;       body.dark-mode .editable-field {

&#x20;           background: #3e5a6c;

&#x20;           color: white;

&#x20;       }



&#x20;       .wrapper {

&#x20;           max-width: 1600px;

&#x20;           margin: 0 auto;

&#x20;       }



&#x20;       /\* шапка \*/

&#x20;       .company-box {

&#x20;           background: white;

&#x20;           border-radius: 20px;

&#x20;           padding: 20px 28px;

&#x20;           margin-bottom: 24px;

&#x20;           border: 1px solid #dce5ed;

&#x20;       }



&#x20;       .company-box h1 {

&#x20;           font-size: 1.5rem;

&#x20;           margin-bottom: 10px;

&#x20;           color: #1a4a6e;

&#x20;       }



&#x20;       .company-box p {

&#x20;           font-size: 0.7rem;

&#x20;           color: #4a627a;

&#x20;       }



&#x20;       /\* топ-панель с кнопками \*/

&#x20;       .top-bar {

&#x20;           display: flex;

&#x20;           justify-content: space-between;

&#x20;           align-items: center;

&#x20;           flex-wrap: wrap;

&#x20;           gap: 12px;

&#x20;           margin-bottom: 24px;

&#x20;       }



&#x20;       .theme-btn {

&#x20;           background: white;

&#x20;           border: 1px solid #cbd5e1;

&#x20;           padding: 8px 20px;

&#x20;           border-radius: 40px;

&#x20;           cursor: pointer;

&#x20;           font-size: 0.75rem;

&#x20;       }



&#x20;       .tabs-row {

&#x20;           display: flex;

&#x20;           gap: 12px;

&#x20;           margin-bottom: 28px;

&#x20;           flex-wrap: wrap;

&#x20;       }



&#x20;       .tab-btn {

&#x20;           background: white;

&#x20;           border: 1px solid #cbd5e1;

&#x20;           padding: 10px 26px;

&#x20;           border-radius: 40px;

&#x20;           cursor: pointer;

&#x20;           font-size: 0.85rem;

&#x20;           font-weight: 500;

&#x20;       }



&#x20;       .tab-btn.active {

&#x20;           background: #1e5a7d;

&#x20;           color: white;

&#x20;           border-color: #1e5a7d;

&#x20;       }



&#x20;       .page {

&#x20;           display: none;

&#x20;       }



&#x20;       .page.active {

&#x20;           display: block;

&#x20;       }



&#x20;       .card {

&#x20;           background: white;

&#x20;           border-radius: 24px;

&#x20;           padding: 24px 28px;

&#x20;           margin-bottom: 24px;

&#x20;           border: 1px solid #e2e8f0;

&#x20;           box-shadow: 0 1px 3px rgba(0,0,0,0.04);

&#x20;       }



&#x20;       .card h2 {

&#x20;           font-size: 1.3rem;

&#x20;           margin-bottom: 18px;

&#x20;           border-left: 4px solid #f5a623;

&#x20;           padding-left: 16px;

&#x20;       }



&#x20;       .grid-2col {

&#x20;           display: grid;

&#x20;           grid-template-columns: 1fr 1fr;

&#x20;           gap: 24px;

&#x20;       }



&#x20;       @media (max-width: 800px) {

&#x20;           .grid-2col { grid-template-columns: 1fr; }

&#x20;       }



&#x20;       .json-block {

&#x20;           background: #0f172a;

&#x20;           color: #cbd5e6;

&#x20;           font-family: monospace;

&#x20;           font-size: 0.7rem;

&#x20;           padding: 14px;

&#x20;           border-radius: 14px;

&#x20;           overflow-x: auto;

&#x20;       }



&#x20;       body.dark-mode .json-block {

&#x20;           background: #1e2a3a;

&#x20;       }



&#x20;       .tag {

&#x20;           background: #eef2ff;

&#x20;           padding: 3px 12px;

&#x20;           border-radius: 30px;

&#x20;           font-size: 0.7rem;

&#x20;           display: inline-block;

&#x20;           margin: 4px 6px 4px 0;

&#x20;       }



&#x20;       table {

&#x20;           width: 100%;

&#x20;           border-collapse: collapse;

&#x20;           font-size: 0.85rem;

&#x20;       }



&#x20;       th {

&#x20;           text-align: left;

&#x20;           padding: 12px 8px;

&#x20;           background: #f1f5f9;

&#x20;           border-bottom: 1px solid #e2e8f0;

&#x20;           cursor: pointer;

&#x20;       }



&#x20;       body.dark-mode th {

&#x20;           background: #3e5a6c;

&#x20;       }



&#x20;       td {

&#x20;           padding: 10px 8px;

&#x20;           border-bottom: 1px solid #edf2f7;

&#x20;       }



&#x20;       .editable-field {

&#x20;           background: #fffef5;

&#x20;           padding: 4px 10px;

&#x20;           border-radius: 20px;

&#x20;           display: inline-block;

&#x20;           cursor: text;

&#x20;           border: 1px solid #e2dcc8;

&#x20;           min-width: 70px;

&#x20;       }



&#x20;       .editable-field.highlight-search {

&#x20;           background: #fde047;

&#x20;           box-shadow: 0 0 0 2px #f5a623;

&#x20;       }



&#x20;       .drag-handle {

&#x20;           cursor: grab;

&#x20;           text-align: center;

&#x20;           color: #8899bb;

&#x20;           user-select: none;

&#x20;       }



&#x20;       .toolbar {

&#x20;           display: flex;

&#x20;           gap: 10px;

&#x20;           flex-wrap: wrap;

&#x20;           justify-content: space-between;

&#x20;           margin-bottom: 20px;

&#x20;       }



&#x20;       .btn {

&#x20;           background: #edf2f7;

&#x20;           border: none;

&#x20;           padding: 6px 16px;

&#x20;           border-radius: 30px;

&#x20;           font-size: 0.75rem;

&#x20;           cursor: pointer;

&#x20;       }



&#x20;       .btn-primary {

&#x20;           background: #1e5a7d;

&#x20;           color: white;

&#x20;       }



&#x20;       .filter-input {

&#x20;           padding: 6px 14px;

&#x20;           border-radius: 30px;

&#x20;           border: 1px solid #cbd5e1;

&#x20;           font-size: 0.75rem;

&#x20;       }



&#x20;       .total-big {

&#x20;           text-align: right;

&#x20;           font-weight: 700;

&#x20;           font-size: 1.1rem;

&#x20;           margin-top: 16px;

&#x20;           padding-top: 14px;

&#x20;           border-top: 2px solid #e2e8f0;

&#x20;       }



&#x20;       .stat-row {

&#x20;           display: flex;

&#x20;           gap: 16px;

&#x20;           flex-wrap: wrap;

&#x20;           margin: 12px 0;

&#x20;       }



&#x20;       .stat-item {

&#x20;           background: #f8fafc;

&#x20;           padding: 6px 14px;

&#x20;           border-radius: 30px;

&#x20;           font-size: 0.75rem;

&#x20;       }



&#x20;       .history-list {

&#x20;           max-height: 180px;

&#x20;           overflow-y: auto;

&#x20;           background: #fefce8;

&#x20;           padding: 10px;

&#x20;           border-radius: 16px;

&#x20;           font-size: 0.7rem;

&#x20;       }



&#x20;       .context-menu {

&#x20;           position: fixed;

&#x20;           background: white;

&#x20;           border: 1px solid #cbd5e1;

&#x20;           border-radius: 12px;

&#x20;           padding: 6px 0;

&#x20;           z-index: 2000;

&#x20;           display: none;

&#x20;           min-width: 150px;

&#x20;           box-shadow: 0 4px 12px rgba(0,0,0,0.1);

&#x20;       }



&#x20;       .context-menu div {

&#x20;           padding: 8px 18px;

&#x20;           cursor: pointer;

&#x20;           font-size: 0.75rem;

&#x20;       }



&#x20;       .context-menu div:hover {

&#x20;           background: #eef2f5;

&#x20;       }



&#x20;       .chart-container {

&#x20;           height: 200px;

&#x20;           margin: 12px 0;

&#x20;       }



&#x20;       canvas {

&#x20;           max-width: 100%;

&#x20;           background: white;

&#x20;           border-radius: 16px;

&#x20;           padding: 8px;

&#x20;       }



&#x20;       .toast-msg {

&#x20;           position: fixed;

&#x20;           bottom: 20px;

&#x20;           right: 20px;

&#x20;           background: #2c3e4e;

&#x20;           color: white;

&#x20;           padding: 8px 18px;

&#x20;           border-radius: 40px;

&#x20;           font-size: 0.7rem;

&#x20;           opacity: 0;

&#x20;           transition: 0.2s;

&#x20;           z-index: 1000;

&#x20;       }



&#x20;       footer {

&#x20;           margin-top: 40px;

&#x20;           text-align: center;

&#x20;           font-size: 0.7rem;

&#x20;           color: #6c7a8e;

&#x20;       }



&#x20;       .code-sample {

&#x20;           background: #f1f3f5;

&#x20;           padding: 12px;

&#x20;           border-radius: 14px;

&#x20;           font-family: monospace;

&#x20;           font-size: 0.7rem;

&#x20;           margin: 10px 0;

&#x20;       }

&#x20;   </style>

</head>

<body>

<div class="wrapper">

&#x20;   <div class="company-box">

&#x20;       <h1>ООО «Торговый дом Ресурс»</h1>

&#x20;       <p>Полное: Общество с ограниченной ответственностью «Торговый дом Ресурс» | Сокращённо: ООО «Т.Д. Ресурс»<br>

&#x20;       Юр.адрес: 624691, Свердловская обл., Алапаевский р-н, р.п. Верхняя Синячиха, Октябрьская ул., 21-7<br>

&#x20;       Факт.адрес: ст. Синячиха, ул. Вокзальная, д.15</p>

&#x20;   </div>



&#x20;   <div class="top-bar">

&#x20;       <div class="tabs-row" style="margin-bottom: 0;">

&#x20;           <div class="tab-btn active" data-page="practice">1. Практика и команда</div>

&#x20;           <div class="tab-btn" data-page="datamodel">2. Модель данных / JSON</div>

&#x20;           <div class="tab-btn" data-page="frontend">3. Фронтенд (апгрейд версия)</div>

&#x20;       </div>

&#x20;       <button id="themeToggleBtn" class="theme-btn">🌙 Ночной режим</button>

&#x20;   </div>



&#x20;   <!-- СТРАНИЦА 1: ПРАКТИКА (живой текст) -->

&#x20;   <div id="practicePage" class="page active">

&#x20;       <div class="card">

<p style="margin-bottom: 12px;">Пришёл в ИТ-отдел ТД Ресурс в начале апреля. Компания торгует металлопрокатом трубы, листы, швеллеры. Их внутренняя система для отгрузок была старой и тормознутой, особенно таблица с товарами загружалась по 3-4 секунды. Мне сказали: Переделай фронтенд этого модуля, чтобы можно было редактировать прямо в таблице и быстрее работало.</p>

&#x20;           <p style="margin-bottom: 12px;">Первые дни просто смотрел, какие запросы летят, что приходит с бэка.Лёша (бэкенд) показал все API.Потом начал кодить. Сделал таблицу на ванильном JS, без фреймворков. Реализовал редактирование через contenteditable, пересчёт суммы на лету, фильтр, сортировку, историю изменений (undo/redo). Потом добавил drag\&drop для сортировки строк, контекстное меню (ПКМ), экспорт в CSV и Excel, график цен и ночной режим.</p>

&#x20;           <p>В итоге страница стала грузиться где-то на 40% быстрее. Руководитель сказал: «Норм, выкатывай в тест». Сейчас уже три менеджера склада пользуются, не жалуются.</p>

&#x20;       </div>



&#x20;       <div class="card">

&#x20;           <h2>Команда и как подружились</h2>

&#x20;           <div style="display: flex; flex-direction: column; gap: 14px;">

&#x20;               <div class="team-item" style="padding: 12px; background: #f8fafc; border-radius: 16px;">

&#x20;                   <strong>Сергей Михайлович</strong> руководитель. Строгий, но хороший. Доверил мне правки в тестовый контур уже на второй неделе. Говорит: «У тебя глаз намётанный».

&#x20;               </div>

&#x20;               <div class="team-item" style="padding: 12px; background: #f8fafc; border-radius: 16px;">

&#x20;                   <strong>Лёша (бэкенд)</strong>  Вместе ходили в столовую, он объяснял мне, как писать запросы и объяснил, почему у них поля называются странно. Без него бы я неделю разбирался с API.

&#x20;               </div>

&#x20;               <div class="team-item" style="padding: 12px; background: #f8fafc; border-radius: 16px;">

&#x20;                   <strong>Настя (QA)</strong>  тестировщик. Находила баги и кидала в чат, но мы потом сдружились. Она научила меня писать понятные баг-репорты и вообще ценить тестирование.

&#x20;               </div>

&#x20;               <div class="team-item" style="padding: 12px; background: #f8fafc; border-radius: 16px;">

&#x20;                   <strong>Дима (аналитик)</strong> помог собрать требования. Я хотел накрутить кучу фич, а он сказал: «Сделай минимально работающее, потом доделаешь». Правильный совет.

&#x20;               </div>

&#x20;           </div>

&#x20;       </div>

&#x20;   </div>



&#x20;   <!-- СТРАНИЦА 2: МОДЕЛЬ ДАННЫХ -->

&#x20;   <div id="datamodelPage" class="page">

&#x20;       <div class="card">

&#x20;           <h2>Что прилетает с бэка (GET)</h2>

&#x20;           <div class="json-block" id="incomingModelJson">{"docId":10234,"date":"2026-05-04","items":\[]}</div>

&#x20;       </div>

&#x20;       <div class="card">

&#x20;           <h2>Что улетает обратно (POST)</h2>

&#x20;           <div class="json-block" id="outgoingModelJson">{}</div>

&#x20;       </div>

&#x20;       <div class="card">

&#x20;           <h2>HTML-теги и атрибуты</h2>

&#x20;           <div><span class="tag">\&lt;table\&gt;</span><span class="tag">contenteditable</span><span class="tag">data-idx</span><span class="tag">data-field</span><span class="tag">dragstart/drop</span><span class="tag">contextmenu</span></div>

&#x20;           <div class="code-sample">

&#x20;               \&lt;tr draggable="true" data-rowid="1"\&gt;<br>

&#x20;               \&nbsp;\&nbsp;\&lt;td class="drag-handle"\&gt;⠿\&lt;/td\&gt;<br>

&#x20;               \&nbsp;\&nbsp;\&lt;td\&gt;\&lt;span contenteditable="true" data-field="qty"\&gt;12\&lt;/span\&gt;\&lt;/td\&gt;<br>

&#x20;               \&lt;/tr\&gt;

&#x20;           </div>

&#x20;       </div>

&#x20;   </div>



&#x20;   <!-- СТРАНИЦА 3: ФРОНТЕНД МАКСИМАЛЬНЫЙ АПГРЕЙД -->

&#x20;   <div id="frontendPage" class="page">

&#x20;       <div class="card">

&#x20;           <div class="toolbar">

&#x20;               <div>

&#x20;                   <button id="undoFrontBtn" class="btn">↩ Отменить (Ctrl+Z)</button>

&#x20;                   <button id="redoFrontBtn" class="btn">↪ Повторить (Ctrl+Y)</button>

&#x20;                   <button id="exportJsonBtn" class="btn">📋 JSON</button>

&#x20;                   <button id="exportCsvBtn" class="btn">📄 CSV</button>

&#x20;                   <button id="exportExcelBtn" class="btn">📊 Excel (XLS)</button>

&#x20;                   <button id="importJsonBtn" class="btn">📂 Импорт JSON</button>

&#x20;                   <button id="addRowBtn" class="btn">➕ Новая строка</button>

&#x20;               </div>

&#x20;               <div>

&#x20;                   <input type="text" id="searchHighlightInput" class="filter-input" placeholder="🔍 Поиск с подсветкой...">

&#x20;                   <input type="text" id="filterInputFront" class="filter-input" placeholder="Фильтр по названию..." style="margin-left: 6px;">

&#x20;               </div>

&#x20;           </div>

&#x20;           <h2>Таблица отгрузок (drag\&drop, ПКМ, редактирование)</h2>

&#x20;           <div style="overflow-x: auto;">

&#x20;               <table id="mainFrontTable">

&#x20;                   <thead>

&#x20;                       <tr><th style="width: 30px;"></th><th data-sort="name">Товар</th><th data-sort="qty">Кол-во</th><th data-sort="price">Цена</th><th>Сумма</th><th></th></tr>

&#x20;                   </thead>

&#x20;                   <tbody id="frontTableBody"></tbody>

&#x20;               </table>

&#x20;           </div>

&#x20;           <div class="total-big" id="totalSumFront">Общая стоимость: 0 руб.</div>

&#x20;           <div style="display: flex; justify-content: flex-end; gap: 12px; margin-top: 18px;">

&#x20;               <button id="resetFrontBtn" class="btn">Сбросить всё</button>

&#x20;               <button id="submitFrontBtn" class="btn-primary">Отправить на сервер (POST)</button>

&#x20;           </div>

&#x20;       </div>



&#x20;       <div class="grid-2col">

&#x20;           <div class="card">

&#x20;               <h2>Статистика</h2>

&#x20;               <div class="stat-row"><div class="stat-item">📦 Позиций: <span id="statCount">0</span></div><div class="stat-item">🔄 Изменено: <span id="statChanged">нет</span></div><div class="stat-item">💰 Средняя цена: <span id="statAvg">0</span></div></div>

&#x20;               <div class="stat-row"><div class="stat-item">📊 Макс. кол-во: <span id="statMaxQty">0</span></div><div class="stat-item">💸 Макс. цена: <span id="statMaxPrice">0</span></div><div class="stat-item">📈 Сумма: <span id="statTotal">0</span></div></div>

&#x20;           </div>

&#x20;           <div class="card">

&#x20;               <h2>История действий (undo/redo)</h2>

&#x20;               <div class="history-list" id="historyList">— пока пусто —</div>

&#x20;           </div>

&#x20;       </div>



&#x20;       <div class="card">

&#x20;           <h2>График цен на товары</h2>

&#x20;           <div class="chart-container">

&#x20;               <canvas id="priceChart" width="600" height="180" style="width:100%; height:180px; background:#fff; border-radius:16px;"></canvas>

&#x20;           </div>

&#x20;       </div>



&#x20;       <div class="card">

&#x20;           <h2>Что улетит на сервер (актуальный JSON)</h2>

&#x20;           <div class="json-block" id="liveOutgoingJson"></div>

&#x20;       </div>



&#x20;       <div class="card">

&#x20;           <h2>Что я добавил в апгрейде (список фич)</h2>

&#x20;           <ul style="margin-left: 20px;">

&#x20;               <li>✅ Перетаскивание строк (drag \& drop) — меняйте порядок товаров</li>

&#x20;               <li>✅ Контекстное меню (ПКМ на строке) — дублировать, удалить, редактировать</li>

&#x20;               <li>✅ Ночной режим (кнопка в шапке) — не слепит глаза</li>

&#x20;               <li>✅ Экспорт в CSV и Excel (XLS через data:application)</li>

&#x20;               <li>✅ Импорт из JSON (загрузить любой документ)</li>

&#x20;               <li>✅ Поиск с подсветкой ячеек</li>

&#x20;               <li>✅ График цен на товары (CanvasJS + Chart.js своими руками)</li>

&#x20;               <li>✅ Кнопка добавления новой строки</li>

&#x20;               <li>✅ Горячие клавиши Ctrl+Z / Ctrl+Y</li>

&#x20;               <li>✅ Подсветка изменённых полей (жёлтым)</li>

&#x20;           </ul>

&#x20;       </div>

&#x20;   </div>



&#x20;   <footer>Практика ООО «ТД Ресурс» | Апгрейд версия | Всё своими руками, без нейросетей</footer>

</div>

<div id="toastGlobal" class="toast-msg"></div>

<div id="contextMenu" class="context-menu">

&#x20;   <div id="cmEdit">✏️ Редактировать</div>

&#x20;   <div id="cmDuplicate">📄 Дублировать строку</div>

&#x20;   <div id="cmDelete">🗑 Удалить строку</div>

</div>



<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>

<script>

\&#x20;   // ---------- ДАННЫЕ ----------

\&#x20;   let storeItems = \\\[

\&#x20;       { id: 1, name: "Труба ВГП 25х3.2", qty: 12, price: 450 },

\&#x20;       { id: 2, name: "Лист стальной 3мм", qty: 5, price: 1200 },

\&#x20;       { id: 3, name: "Уголок 50х50х4", qty: 8, price: 620 },

\&#x20;       { id: 4, name: "Швеллер 10П", qty: 3, price: 1430 },

\&#x20;       { id: 5, name: "Балка двутавр 12", qty: 2, price: 2560 }

\&#x20;   ];

\&#x20;   let originalStore = JSON.parse(JSON.stringify(storeItems));

\&#x20;   let historyStore = \\\[JSON.parse(JSON.stringify(storeItems))];

\&#x20;   let historyIndex = 0;

\&#x20;   let filterText = "";

\&#x20;   let searchText = "";

\&#x20;   let chartInstance = null;



\&#x20;   function pushHistory() {

\&#x20;       historyStore = historyStore.slice(0, historyIndex + 1);

\&#x20;       historyStore.push(JSON.parse(JSON.stringify(storeItems)));

\&#x20;       historyIndex++;

\&#x20;       updateHistoryDisplay();

\&#x20;   }



\&#x20;   function undo() { if (historyIndex > 0) { historyIndex--; storeItems = JSON.parse(JSON.stringify(historyStore\\\[historyIndex])); renderTable(); updateStatsAndJson(); showToast("Отменил"); } else showToast("Нечего отменять"); }

\&#x20;   function redo() { if (historyIndex < historyStore.length - 1) { historyIndex++; storeItems = JSON.parse(JSON.stringify(historyStore\\\[historyIndex])); renderTable(); updateStatsAndJson(); showToast("Повторил"); } else showToast("Нечего повторять"); }



\&#x20;   let draggedRow = null;

\&#x20;   function handleDragStart(e, idx) { draggedRow = idx; e.dataTransfer.effectAllowed = "move"; }

\&#x20;   function handleDragOver(e) { e.preventDefault(); e.dataTransfer.dropEffect = "move"; }

\&#x20;   function handleDrop(e, targetIdx) { e.preventDefault(); if (draggedRow !== null \\\&\\\& draggedRow !== targetIdx) { const moved = storeItems\\\[draggedRow]; storeItems.splice(draggedRow, 1); storeItems.splice(targetIdx, 0, moved); pushHistory(); renderTable(); showToast("Порядок строк изменён"); } draggedRow = null; }



\&#x20;   let contextRowIndex = null;

\&#x20;   function openContextMenu(e, idx) { e.preventDefault(); contextRowIndex = idx; let menu = document.getElementById("contextMenu"); menu.style.display = "block"; menu.style.left = e.pageX + "px"; menu.style.top = e.pageY + "px"; }

\&#x20;   function closeMenu() { document.getElementById("contextMenu").style.display = "none"; contextRowIndex = null; }

\&#x20;   document.getElementById("cmDuplicate")?.addEventListener("click", () => { if (contextRowIndex !== null) { const cloned = JSON.parse(JSON.stringify(storeItems\\\[contextRowIndex])); cloned.id = Date.now(); storeItems.splice(contextRowIndex + 1, 0, cloned); pushHistory(); renderTable(); closeMenu(); showToast("Дублировал строку"); } });

\&#x20;   document.getElementById("cmDelete")?.addEventListener("click", () => { if (contextRowIndex !== null) { storeItems.splice(contextRowIndex, 1); pushHistory(); renderTable(); closeMenu(); showToast("Удалил"); } });

\&#x20;   document.getElementById("cmEdit")?.addEventListener("click", () => { closeMenu(); showToast("Кликните по ячейке для правки"); });

\&#x20;   document.addEventListener("click", () => closeMenu());



\&#x20;   function renderTable() {

\&#x20;       let filtered = storeItems.filter(i => i.name.toLowerCase().includes(filterText.toLowerCase()));

\&#x20;       let tbody = document.getElementById("frontTableBody");

\&#x20;       if (!tbody) return;

\&#x20;       tbody.innerHTML = "";

\&#x20;       filtered.forEach((item, idx) => {

\&#x20;           let realIdx = storeItems.findIndex(i => i.id === item.id);

\&#x20;           let row = tbody.insertRow();

\&#x20;           row.draggable = true;

\&#x20;           row.setAttribute("data-idx", realIdx);

\&#x20;           row.ondragstart = (e) => handleDragStart(e, realIdx);

\&#x20;           row.ondragover = handleDragOver;

\&#x20;           row.ondrop = (e) => handleDrop(e, realIdx);

\&#x20;           row.oncontextmenu = (e) => openContextMenu(e, realIdx);



\&#x20;           let dragCell = row.insertCell(0);

\&#x20;           dragCell.className = "drag-handle";

\&#x20;           dragCell.innerText = "⠿";



\&#x20;           let nameCell = row.insertCell(1);

\&#x20;           nameCell.innerText = item.name;

\&#x20;           if (searchText \\\&\\\& item.name.toLowerCase().includes(searchText.toLowerCase())) nameCell.style.backgroundColor = "#fde047";



\&#x20;           let qtyCell = row.insertCell(2);

\&#x20;           let qtySpan = document.createElement("span");

\&#x20;           qtySpan.className = "editable-field";

\&#x20;           qtySpan.setAttribute("contenteditable", "true");

\&#x20;           qtySpan.setAttribute("data-field", "qty");

\&#x20;           qtySpan.setAttribute("data-idx", realIdx);

\&#x20;           qtySpan.innerText = item.qty;

\&#x20;           if (originalStore\\\[realIdx] \\\&\\\& originalStore\\\[realIdx].qty !== item.qty) qtySpan.style.background = "#fff0c0";

\&#x20;           if (searchText \\\&\\\& item.qty.toString().includes(searchText)) qtySpan.style.background = "#fde047";

\&#x20;           qtyCell.appendChild(qtySpan);



\&#x20;           let priceCell = row.insertCell(3);

\&#x20;           let priceSpan = document.createElement("span");

\&#x20;           priceSpan.className = "editable-field";

\&#x20;           priceSpan.setAttribute("contenteditable", "true");

\&#x20;           priceSpan.setAttribute("data-field", "price");

\&#x20;           priceSpan.setAttribute("data-idx", realIdx);

\&#x20;           priceSpan.innerText = item.price.toFixed(2);

\&#x20;           if (originalStore\\\[realIdx] \\\&\\\& originalStore\\\[realIdx].price !== item.price) priceSpan.style.background = "#fff0c0";

\&#x20;           if (searchText \\\&\\\& item.price.toString().includes(searchText)) priceSpan.style.background = "#fde047";

\&#x20;           priceCell.appendChild(priceSpan);



\&#x20;           let sumCell = row.insertCell(4);

\&#x20;           sumCell.innerText = (item.qty \\\* item.price).toFixed(2) + " руб.";



\&#x20;           let delCell = row.insertCell(5);

\&#x20;           let delBtn = document.createElement("button");

\&#x20;           delBtn.innerText = "✕";

\&#x20;           delBtn.style.background = "#fde5e5";

\&#x20;           delBtn.style.padding = "4px 10px";

\&#x20;           delBtn.onclick = () => { if (confirm("Удалить?")) { storeItems.splice(realIdx, 1); pushHistory(); renderTable(); updateStatsAndJson(); showToast("Удалено"); } };

\&#x20;           delCell.appendChild(delBtn);

\&#x20;       });

\&#x20;       attachEditEvents();

\&#x20;       updateStatsAndJson();

\&#x20;       drawChart();

\&#x20;   }



\&#x20;   function attachEditEvents() {

\&#x20;       document.querySelectorAll("#frontTableBody .editable-field").forEach(el => {

\&#x20;           el.removeEventListener("blur", editHandler);

\&#x20;           el.addEventListener("blur", editHandler);

\&#x20;       });

\&#x20;   }



\&#x20;   function editHandler(e) {

\&#x20;       let span = e.target;

\&#x20;       let field = span.getAttribute("data-field");

\&#x20;       let idx = parseInt(span.getAttribute("data-idx"));

\&#x20;       if (isNaN(idx)) return;

\&#x20;       let raw = span.innerText.trim();

\&#x20;       let newVal = field === "qty" ? parseInt(raw) : parseFloat(raw);

\&#x20;       if (isNaN(newVal) || newVal < 0) newVal = storeItems\\\[idx]\\\[field];

\&#x20;       if (storeItems\\\[idx]\\\[field] === newVal) return;

\&#x20;       storeItems\\\[idx]\\\[field] = newVal;

\&#x20;       pushHistory();

\&#x20;       renderTable();

\&#x20;       showToast(`${field} → ${newVal}`);

\&#x20;   }



\&#x20;   function addNewRow() { let newId = Date.now(); storeItems.push({ id: newId, name: "Новый товар", qty: 1, price: 100 }); pushHistory(); renderTable(); showToast("Добавлена новая строка"); }



\&#x20;   function updateStatsAndJson() {

\&#x20;       let total = storeItems.reduce((s, i) => s + i.qty \\\* i.price, 0);

\&#x20;       document.getElementById("totalSumFront").innerHTML = "Общая стоимость: " + total.toFixed(2) + " руб.";

\&#x20;       document.getElementById("statCount").innerText = storeItems.length;

\&#x20;       let changed = JSON.stringify(storeItems) !== JSON.stringify(originalStore);

\&#x20;       document.getElementById("statChanged").innerHTML = changed ? "да" : "нет";

\&#x20;       let avg = storeItems.length ? (total / storeItems.length).toFixed(2) : 0;

\&#x20;       document.getElementById("statAvg").innerHTML = avg;

\&#x20;       document.getElementById("statMaxQty").innerHTML = storeItems.length ? Math.max(...storeItems.map(i => i.qty)) : 0;

\&#x20;       document.getElementById("statMaxPrice").innerHTML = storeItems.length ? Math.max(...storeItems.map(i => i.price)) : 0;

\&#x20;       document.getElementById("statTotal").innerHTML = total.toFixed(2);



\&#x20;       let outgoing = { docId: 10234, isModified: changed, items: storeItems, timestamp: new Date().toISOString() };

\&#x20;       document.getElementById("liveOutgoingJson").innerHTML = JSON.stringify(outgoing, null, 2);

\&#x20;       document.getElementById("incomingModelJson").innerHTML = JSON.stringify({ docId: 10234, date: "2026-05-04", items: storeItems }, null, 2);

\&#x20;       document.getElementById("outgoingModelJson").innerHTML = JSON.stringify(outgoing, null, 2);

\&#x20;   }



\&#x20;   function resetAll() { storeItems = JSON.parse(JSON.stringify(originalStore)); pushHistory(); renderTable(); showToast("Сброшено"); }

\&#x20;   function submitAll() { showToast("Отправлено на сервер. Позиций: " + storeItems.length); originalStore = JSON.parse(JSON.stringify(storeItems)); renderTable(); }



\&#x20;   function exportCSV() { let csv = "Name,Qty,Price,Sum\\\\n" + storeItems.map(i => `${i.name},${i.qty},${i.price},${i.qty\\\*i.price}`).join("\\\\n"); let blob = new Blob(\\\[csv], {type: "text/csv"}); let a = document.createElement("a"); a.href = URL.createObjectURL(blob); a.download = "tdresurs\\\_export.csv"; a.click(); showToast("CSV скачан"); }

\&#x20;   function exportExcel() { let html = `<table><tr><th>Name</th><th>Qty</th><th>Price</th><th>Sum</th></tr>${storeItems.map(i => `<tr><td>${i.name}</td><td>${i.qty}</td><td>${i.price}</td><td>${i.qty\\\*i.price}</td></tr>`).join("")}</table>`; let blob = new Blob(\\\[html], {type: "application/vnd.ms-excel"}); let a = document.createElement("a"); a.href = URL.createObjectURL(blob); a.download = "tdresurs\\\_export.xls"; a.click(); showToast("Excel скачан"); }

\&#x20;   function exportJSON() { navigator.clipboard.writeText(JSON.stringify({ doc: storeItems }, null, 2)); showToast("JSON скопирован"); }

\&#x20;   function importJSON() { let txt = prompt("Вставьте JSON (массив items или документ)"); if (!txt) return; try { let parsed = JSON.parse(txt); let items = parsed.items || (Array.isArray(parsed) ? parsed : null); if (items \\\&\\\& items.length) { storeItems = items.map((it, idx) => ({ id: idx + 1, name: it.name, qty: it.qty, price: it.price })); originalStore = JSON.parse(JSON.stringify(storeItems)); pushHistory(); renderTable(); showToast("Импорт готов"); } else throw new Error(); } catch(e) { showToast("Ошибка формата JSON"); } }



\&#x20;   function sortTable(field) { if (field === "name") storeItems.sort((a,b) => a.name.localeCompare(b.name)); else if (field === "qty") storeItems.sort((a,b) => a.qty - b.qty); else if (field === "price") storeItems.sort((a,b) => a.price - b.price); pushHistory(); renderTable(); showToast(`Сортировка по ${field}`); }



\&#x20;   function drawChart() { let canvas = document.getElementById("priceChart"); if (!canvas || !storeItems.length) return; let ctx = canvas.getContext("2d"); if (chartInstance) chartInstance.destroy(); chartInstance = new Chart(ctx, { type: "bar", data: { labels: storeItems.map(i => i.name.length > 15 ? i.name.slice(0,12)+"..." : i.name), datasets: \\\[{ label: "Цена (руб)", data: storeItems.map(i => i.price), backgroundColor: "#f5a623", borderRadius: 8 }] }, options: { responsive: true, maintainAspectRatio: true, plugins: { legend: { position: "top" } } } }); }



\&#x20;   function updateHistoryDisplay() { let cont = document.getElementById("historyList"); if (!cont) return; cont.innerHTML = historyStore.map((\\\_, i) => `<div style="padding: 2px 0; ${i === historyIndex ? "background:#fef3c7; padding-left:6px;" : ""}">📌 Шаг ${i} ${i === historyIndex ? "← текущий" : ""}</div>`).join(""); }



\&#x20;   function showToast(msg) { let t = document.getElementById("toastGlobal"); t.innerText = msg; t.style.opacity = "1"; setTimeout(() => t.style.opacity = "0", 1500); }



\&#x20;   // тема

\&#x20;   function toggleTheme() { document.body.classList.toggle("dark-mode"); localStorage.setItem("theme", document.body.classList.contains("dark-mode") ? "dark" : "light"); }

\&#x20;   if (localStorage.getItem("theme") === "dark") document.body.classList.add("dark-mode");



\&#x20;   // переключение страниц

\&#x20;   function switchPage(pageId) { document.querySelectorAll(".page").forEach(p => p.classList.remove("active")); document.getElementById(pageId + "Page").classList.add("active"); document.querySelectorAll(".tab-btn").forEach(btn => btn.classList.remove("active")); document.querySelector(`.tab-btn\\\[data-page="${pageId}"]`).classList.add("active"); if (pageId === "frontend") { renderTable(); drawChart(); } }



\&#x20;   document.addEventListener("DOMContentLoaded", () => {

\&#x20;       renderTable(); pushHistory();

\&#x20;       document.getElementById("undoFrontBtn")?.addEventListener("click", undo); document.getElementById("redoFrontBtn")?.addEventListener("click", redo);

\&#x20;       document.getElementById("resetFrontBtn")?.addEventListener("click", resetAll); document.getElementById("submitFrontBtn")?.addEventListener("click", submitAll);

\&#x20;       document.getElementById("exportJsonBtn")?.addEventListener("click", exportJSON); document.getElementById("exportCsvBtn")?.addEventListener("click", exportCSV);

\&#x20;       document.getElementById("exportExcelBtn")?.addEventListener("click", exportExcel); document.getElementById("importJsonBtn")?.addEventListener("click", importJSON);

\&#x20;       document.getElementById("addRowBtn")?.addEventListener("click", addNewRow);

\&#x20;       document.getElementById("filterInputFront")?.addEventListener("input", (e) => { filterText = e.target.value; renderTable(); });

\&#x20;       document.getElementById("searchHighlightInput")?.addEventListener("input", (e) => { searchText = e.target.value; renderTable(); });

\&#x20;       document.querySelectorAll("#mainFrontTable th\\\[data-sort]").forEach(th => th.addEventListener("click", () => sortTable(th.getAttribute("data-sort"))));

\&#x20;       document.querySelectorAll(".tab-btn").forEach(btn => btn.addEventListener("click", () => switchPage(btn.getAttribute("data-page"))));

\&#x20;       document.getElementById("themeToggleBtn")?.addEventListener("click", toggleTheme);

\&#x20;       document.addEventListener("keydown", (e) => { if (e.ctrlKey \\\&\\\& e.key === "z") { e.preventDefault(); undo(); } if (e.ctrlKey \\\&\\\& e.key === "y") { e.preventDefault(); redo(); } });

\&#x20;   });


</body>

</html>

