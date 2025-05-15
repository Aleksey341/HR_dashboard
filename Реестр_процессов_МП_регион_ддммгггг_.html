<!DOCTYPE html>
<html lang="ru" class="scroll-smooth">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Форма опроса v3.2 (Сброс при запуске)</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        primary: '#3b82f6', 
                        accent: '#2563eb',  
                        background: '#f9fafb', 
                        card: '#ffffff',      
                        tooltip: '#eef4ff',   
                        danger: '#ef4444',    
                    },
                    boxShadow: {
                        soft: '0 4px 12px rgba(0,0,0,0.1)'
                    },
                    borderRadius: {
                        xl2: '1rem'
                    },
                    ringOffsetWidth: { '2': '2px', },
                    ringColor: { DEFAULT: '#3b82f6', }
                }
            }
        }
    </script>
    <style>
        .glossary-list dt { font-weight: 600; margin-top: 0.75rem; color: #374151; }
		/* Chrome, Safari, Edge */
input[type="number"]::-webkit-outer-spin-button,
input[type="number"]::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type="number"] {
  -moz-appearance: textfield;
}

        .dark .glossary-list dt { color: #d1d5db; }
        .glossary-list dd { margin-left: 1rem; margin-top: 0.25rem; font-size: 0.875rem; color: #4b5563; }
        .dark .glossary-list dd { color: #9ca3af; }
        .button-loading::after { content: ""; display: inline-block; width: 1em; height: 1em; margin-left: 0.5em; vertical-align: -0.125em; border: 2px solid currentColor; border-left-color: transparent; border-radius: 50%; animation: spin 0.6s linear infinite; }
        @keyframes spin { to { transform: rotate(360deg); } }
        .field-error { border-color: #ef4444 !important; --tw-ring-color: #ef4444 !important; }
        .label-error { color: #ef4444 !important; }
    </style>
</head>
<body class="font-sans bg-background text-gray-800 dark:bg-gray-900 dark:text-gray-100">
    <header class="bg-gradient-to-r from-gray-900 to-blue-900 text-white py-2 px-4 flex flex-col sm:flex-row justify-between items-center shadow-md sticky top-0 z-40">
        <div class="flex items-center space-x-4 mb-2 sm:mb-0">
            <span class="bg-white text-black uppercase px-3 py-1 rounded-full font-semibold text-sm">росмолодёжь</span>
            <span class="text-xs leading-tight text-center sm:text-left">Правительство<br>Липецкой области</span>
        </div>
        <div class="flex items-center space-x-2 sm:space-x-4">
            <button id="clearStorageBtn" aria-label="Начать заново (очистить сохраненные данные)" class="p-2 focus:outline-none text-xl hover:bg-white/10 rounded-full" title="Начать заново (очистить сохраненные данные)">🔄</button>
            <button id="themeToggle" aria-label="Переключить тему" class="p-2 focus:outline-none text-xl hover:bg-white/10 rounded-full">🌙</button>
            <div class="text-xs text-center sm:text-right">АНО "Область будущего"</div>
        </div>
    </header>

    <main class="max-w-3xl mx-auto p-4">
        <div id="progressBar" class="flex justify-center space-x-1 sm:space-x-2 mb-6 overflow-x-auto pb-2"></div>
        <h2 id="stepTitle" class="text-2xl font-bold text-center text-accent dark:text-primary mb-4"></h2>
        <div id="navigation-buttons-top" class="flex flex-col sm:flex-row justify-between items-center mb-6"> 
            <button id="prevBtn" class="w-full sm:w-auto px-6 py-3 bg-gray-400 text-white rounded-xl2 shadow-soft hover:bg-gray-500 disabled:opacity-50 disabled:cursor-not-allowed mb-2 sm:mb-0 transition-colors duration-150" disabled>← Назад</button>
            <div class="w-full sm:w-auto flex flex-col sm:flex-row space-y-2 sm:space-y-0 sm:space-x-2">
                <button id="nextBtn" class="w-full sm:w-auto px-6 py-3 bg-primary text-white rounded-xl2 shadow-soft hover:bg-accent disabled:opacity-50 disabled:cursor-not-allowed transition-colors duration-150">Далее →</button>
                <button id="exportBtn" class="w-full sm:w-auto px-6 py-3 bg-green-500 text-white rounded-xl2 shadow-soft hover:bg-green-600 hidden transition-colors duration-150">Экспорт в Excel</button>
            </div>
        </div>
        <div id="stepDefinitionContainer"></div>
        <section id="formSteps" class="space-y-6"></section>
        <!--
<p id="counterDisplay" class="mt-4 text-center text-sm text-gray-600 dark:text-gray-400"></p>
-->

        <div id="email-block" class="hidden mt-6 p-4 bg-card dark:bg-gray-800 rounded-xl2 shadow-soft border border-gray-200 dark:border-gray-700 text-center">
            <p class="text-gray-700 dark:text-gray-300">Отправьте заполненный файл Excel в свою ветку чата Telegram</p>
            <div class="mt-2">
                <span id="email-text" class="font-mono text-primary dark:text-blue-400 break-all"></span>
                <!--
<button onclick="copyEmail()" class="ml-0 mt-2 sm:ml-4 sm:mt-0 px-4 py-2 bg-accent text-white rounded-xl2 hover:bg-primary transition-colors duration-150 text-sm">
  Копировать Email
</button>
-->

            </div>
        </div>
    </main>
    <div id="toastContainer" class="fixed bottom-6 right-6 space-y-2 z-50 w-full max-w-xs sm:max-w-sm"></div>

    <script src="https://cdn.jsdelivr.net/npm/xlsx@0.18.5/dist/xlsx.full.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/file-saver@2.0.5/dist/FileSaver.min.js"></script>

    <script>
        const STEP_GLOSSARY = 0;
        const STEP_INSTRUCTIONS = 1;
        const STEP_PERSONAL_DATA = 2;
        const STEP_PROCESS_MAIN_INFO = 3;
        const STEP_RELATED_PROCESSES = 4; 
        const STEP_CUSTOMER_BENEFICIARY = 5;
        const STEP_DOCS_RESULTS_KPI = 6;
        const STEP_REPORTS = 7;
        const STEP_WORKFLOW_TECH = 8;

        const stepsData = [
            { 
                icon: "📚",
                title: "Глоссарий терминов",
                fields: [],
                stepDefinitionHtml: `
                    <div class="prose dark:prose-invert max-w-none">
                        <h3 class="text-xl font-semibold text-gray-800 dark:text-gray-200 mb-3">Глоссарий терминов</h3>
                        <dl class="glossary-list">
                            <dt>Процесс</dt>
                            <dd>Последовательность взаимосвязанных действий или шагов, направленных на создание определенного продукта, услуги или достижение конкретного результата в рамках деятельности организации или органа власти.</dd>
                            <dt>Мероприятие</dt>
                            <dd>Отдельное организованное действие или совокупность действий, проводимых в рамках процесса для достижения конкретной цели или получения определенного результата (например, совещание, конференция, проверка, учебное занятие и т.п.). </dd>
                            <dt>Связанный процесс</dt>
                            <dd>Это другой процесс, который имеет непосредственную взаимосвязь или взаимозависимость с рассматриваемым (основным) процессом. </dd>
                            <dt>Исполнитель процесса</dt>
                            <dd>Роль или организация, ответственная за непосредственное выполнение или организацию процесса. В данной форме предлагается выбрать один из вариантов. </dd>
                            <dt>Благополучатель процесса</dt>
                            <dd>Конечный получатель результата процесса. </dd>
                            <dt>Инициирующее событие</dt>
                            <dd>Это сведения или документы, необходимые для начала процесса.</dd>
                            <dt>Результат на выходе</dt>
                            <dd>Это выгода или ценность, которые получаются при завершении процесса.</dd>
                            <dt>Контрольные процедуры</dt>
                            <dd>Это действия или механизмы, которые используются для проверки правильности, своевременности и соответствия стандартам на различных стадиях выполнения процесса (например, согласования, автоматизированные проверки, мониторинг).</dd>
                            <dt>Информационная система</dt>
                            <dd>Это названия систем, платформ или сервисов, которые применяются для выполнения или поддержки данного процесса.</dd>
                            <dt>Макрос</dt>
                            <dd>Последовательность команд или действий, записанная пользователем для автоматического выполнения повторяющихся задач в компьютерной программе. Позволяет выполнять несколько шагов за одно действие, упрощая рутинную работу (например, в программах для работы с электронными таблицами или текстами).</dd>
                            <dt>Роботизация (RPA)</dt>
                            <dd>Это технология, которая использует специальное программное обеспечение (называемое "роботами"), способное имитировать действия человека при работе с компьютером и различными цифровыми системами.</dd>
                            <dt>Искуственный интеллект (ИИ)</dt>
                            <dd>Это способность компьютерных систем выполнять задачи, которые традиционно требуют человеческого ума. К таким задачам относится обучение, распознавание речи и изображений, принятие решений и решение проблем.</dd>
                        </dl>
                    </div>
                `
            },
            { 
                icon: "📝",
                title: "Инструкция по заполнению",
                fields: [],
                stepDefinitionHtml: `
                    <div class="prose dark:prose-invert max-w-none">
                        <h3 class="text-xl font-semibold text-gray-800 dark:text-gray-200 mb-3">Инструкция по заполнению</h3>
                        <ol class="list-decimal list-inside space-y-2 text-gray-700 dark:text-gray-300">
                            <li>Внимательно ознакомьтесь с определениями терминов на предыдущем шаге.</li>
                            <li>Для перехода к следующему шагу используйте кнопку "Далее →". Для возврата к предыдущему шагу — "← Назад".</li>
                            <li>Заполните все обязательные поля на текущем шаге. Обязательными считаются все видимые поля. Поля, ожидающие числовые значения, принимают только неотрицательные цифры.</li>
                            <li>Используйте иконку (ℹ️) рядом с названием поля для просмотра подсказки. Нажмите на иконку еще раз или клавишу 'Escape' (когда иконка в фокусе), чтобы скрыть подсказку.</li>
                            <li>Видимость некоторых полей зависит от вашего выбора в предыдущих полях (например, названия конкретных организаций).</li>
                            <li>Шаг "Связанные процессы" является динамическим. Сначала ответьте, есть ли связанные процессы. Если "Да", вы сможете добавить до 5 процессов.</li>
                            <li>На последнем шаге сбора данных по процессу (шаг "Документооборот и технологии") кнопка "Далее →" изменится на "Добавить процесс". Нажмите ее, чтобы сохранить текущий процесс и начать заполнение данных для следующего. Поля "Регион" и "ФИО заполняющего" будут сохранены автоматически для последующих процессов.</li>
                            <li>После добавления всех процессов, кнопка "Экспорт в Excel" станет активна на последнем шаге сбора данных. Нажмите ее, чтобы скачать файл со всеми введенными процессами (включая текущий, если он заполнен и валиден).</li>
                            <li>После успешного экспорта появится адрес электронной почты, на который необходимо отправить полученный файл.</li>
                            <li>Ваши данные автоматически сохраняются в браузере. Если вы закроете вкладку и откроете ее снова, вы сможете продолжить с того же места. Кнопка 🔄 в шапке позволяет начать все сначала, удалив все сохраненные данные.</li>
                        </ol>
                    </div>
                `
            },
            { 
                icon: "👤", title: "Данные о себе", fields: [
                    { id: "region", label: "Регион", tooltip: "Пример: Липецкая область", placeholder: "Укажите Ваш регион" },
                    { id: "fio",    label: "ФИО заполняющего", tooltip: "Фамилия Имя Отчество полностью", placeholder: "Укажите Ваше ФИО" }
                ]
            },
            { 
                icon: "ℹ️", title: "Основная информация о процессе", fields: [
                    { id: "process_name",        label: "Наименование процесса", tooltip: "Уникальное название, отражающее суть", placeholder: "Название процесса" },
                    { id: "process_description", label: "Цель и описание процесса", tooltip: "Дайте короткое описание процесса и цели процесса", placeholder: "Суть и назначение процесса" },
                    { id: "process_group",       label: "Принадлежность процесса", tooltip: "Административные (бюджет, кадры и др.), Организационные (мероприятия и др.), Коммуникационные (образование, молодежные обьединения и др.), Аналитические (сбор и анализ данных, мониторинг, оценка), Социально-адаптационные (инклюзивные проекты, проф. ориентация и др.), Инновационные (IT, развитие стартапов и др.)", type: "select",
                        options: ["Административные (бюджет, кадры и др.)", "Организационные (мероприятия и др.)", "Коммуникационные (образование, молодежные обьединения и др.)", "Аналитические (сбор и анализ данных, мониторинг, оценка)", "Социально-адаптационные (инклюзивные проекты, проф. ориентация и др.)", "Инновационные (IT, развитие стартапов и др.)"] },
                    { id: "process_category",    label: "Категория", tooltip: "Уровень процесса", type: "select",
                        options: ["Федеральный","Региональный","Муниципальный"] },
                    { id: "organization_type",   label: "Исполнитель процесса", tooltip: "Кто исполняет процесс/организатор процесса", type: "select",
                        options: ["Региональный орган власти","Подведомственная организация"] },
                    { id: "regional_authority_name", label: "Название регионального органа власти", placeholder: "Укажите название органа власти", type: 'text', conditional: true },
                    { id: "subordinate_org_name",  label: "Название подведомственной организации", placeholder: "Укажите название подведомственной организации", type: 'text', conditional: true }
                ]
            },
            { 
                icon: "🔗", 
                title: "Связанные процессы", 
                stepDefinitionHtml: ` 
                    <p class="font-semibold text-gray-700 dark:text-gray-300">Связанный процесс - это другой процесс, который имеет непосредственную взаимосвязь или взаимозависимость с рассматриваемым (основным) процессом.</p>
                    <ul class="list-disc list-inside mt-1 text-sm text-gray-600 dark:text-gray-400"></ul>
                    <p class="mt-2 text-sm text-gray-600 dark:text-gray-400"></p>
                `, 
                fields: [], 
                customRenderFunctionName: 'renderRelatedProcessesStepControls',
                maxRelatedProcesses: 5,
            },
            { 
                icon: "👥", title: "Заказчик и благополучатели процесса", fields: [
                    { id: "process_customer",  label: "Заказчик процесса", tooltip: "Заказчик процесса — это роль того, кто инициирует процесс, а также определяет его цели и ключевые требования", placeholder: "Напишите должность" },
                    { id: "process_client",    label: "Благополучатели процесса", tooltip: "Конечный получатель результата процесса", placeholder: "Целевая аудитория / получатель" },
                    { id: "client_count",      label: "Количество благополучателей (в год)", tooltip: "Благополучатель процесса — основной получатель конечной выгоды/пользы от процесса", placeholder: "Число благополучателей в год", type: "number", min: 0 },
                    { id: "process_instances", label: "Экземпляры процесса (в год)", tooltip: "Примерное количество выполнений процесса за год", placeholder: "Число выполнений / мероприятий", type: "number", min: 0 }
                ]
            },
            { 
                icon: "📑", title: "Документы, результаты, КПЭ", fields: [
                    { id: "docs_in",        label: "Инициирующее событие на входе", tooltip: "Сведения или документы, необходимые для начала процесса", placeholder: "Инициирующее событие/документ" },
                    { id: "result_out",     label: "Результат на выходе", tooltip: "Выгода/ценность которые получаются при завершении процесса", placeholder: "Конечный результат (событие/документ)" },
                    { id: "result_count",   label: "Количество результатов (в год)", tooltip: "Укажите в ед., шт.", placeholder: "Число результатов (за прошлый год)", type: "number", min: 0 },
                    { id: "control_points", label: "Контрольные процедуры", tooltip: "Ключевые этапы контроля выполнения процесса", placeholder: "Укажите процедуры, которые есть в процессе (согласование, автоматизированные контроли) " },
                    { id: "kpi_exists",     label: "Наличие КПЭ", tooltip: "Установлены ли ключевые показатели эффективности?", type: "select", options: ["Да","Нет"] },
                    { id: "kpi_details",    label: "Укажите КПЭ", placeholder: "Название и значение показателя", type: 'text', conditional: true },
                ]
            },
            { 
                icon: "📊", title: "Отчёты", fields: [
                    { id: "reports_generated", label: "Формируемые отчёты", tooltip: "Укажите виды отчетов. Например: Excel, Word, дашборд", placeholder: "Форматы и виды отчетов" }
                ]
            },
            { 
                icon: "💻", title: "Документооборот и технологии", fields: [
                    { id: "paper_count",    label: "Бумажные документы (в год)", tooltip: "Примерное количествово бумажных документов", placeholder: "Количество штук", type: "number", min: 0 },
                    { id: "digital_count",  label: "Электронные документы (в год)", tooltip: "Примерное кол-во электронных документов (не скан-копий)", placeholder: "Количество штук", type: "number", min: 0 },
                    { id: "scan_count",     label: "Скан-копии (в год)", tooltip: "Примерное кол-во создаваемых скан-копий", placeholder: "Количество штук", type: "number", min: 0 },
                    { id: "info_systems",   label: "Информационная система", tooltip: "Используемые ИС (ЕПГУ, СЭД, сайт ведомства и др.)", placeholder: "Названия систем/платформ" },
                    { id: "applied_tech",   label: "Применяемые технологии", tooltip: "Выберите технологии, которые применяются в процессе", type: "checkboxGroup",
                        options: [ "Макросы","Роботизация (RPA)","Искусственный интеллект", "Не применяются"]
                    }
                ]
            }
        ];
        
        let currentStep = 0;
        let submissions = [];
        let formState = {}; 

        const progressBar = document.getElementById('progressBar');
        const stepTitleEl = document.getElementById('stepTitle');
        const formSteps = document.getElementById('formSteps');
        const stepDefinitionContainer = document.getElementById('stepDefinitionContainer');
        const prevBtn = document.getElementById('prevBtn');
        const nextBtn = document.getElementById('nextBtn');
        const exportBtn = document.getElementById('exportBtn');
        const counterDisplay = document.getElementById('counterDisplay');
        const toastContainer = document.getElementById('toastContainer');
        const htmlEl = document.documentElement;
        const themeToggle = document.getElementById('themeToggle');
        const clearStorageBtn = document.getElementById('clearStorageBtn');
        const emailBlock = document.getElementById('email-block');

        const LS_FORM_STATE_KEY = 'surveyFormState_v3_full_content_FRESH'; 
        const LS_SUBMISSIONS_KEY = 'surveySubmissions_v3_full_content_FRESH';
        const LS_CURRENT_STEP_KEY = 'surveyCurrentStep_v3_full_content_FRESH';
        const LS_THEME_KEY = 'surveyTheme_v3_full_content_FRESH'; 

        document.addEventListener('DOMContentLoaded', () => {
            console.log('DOM fully loaded and parsed - Initializing FRESH state.'); 
            
            currentStep = STEP_GLOSSARY; 
            formState = { hasRelatedProcesses: null, relatedProcessesArray: [] }; 
            submissions = []; 
            
            console.log('Initial state FORCED: currentStep:', currentStep, 'formState:', JSON.parse(JSON.stringify(formState)), 'submissions:', submissions.length);
            
            applySavedTheme(); 
            themeToggle.addEventListener('click', toggleTheme);
            clearStorageBtn.addEventListener('click', clearLocalStorageAndReset); 
            prevBtn.addEventListener('click', handlePrevClick);
            nextBtn.addEventListener('click', handleNextClickOrAddProcess);
            exportBtn.addEventListener('click', exportToExcelHandler);
            document.addEventListener('keydown', handleGlobalKeyDown);
            
            renderAll(); 
            // updateCounter(); 
        });

        function renderAll() { 
            console.log('renderAll called. Current step:', currentStep);
            renderProgress(); 
            renderStep(); 
        }
        
        /*
        function loadStateFromLocalStorage() {
            const savedFormState = localStorage.getItem(LS_FORM_STATE_KEY);
            const savedSubmissions = localStorage.getItem(LS_SUBMISSIONS_KEY);
            const savedCurrentStep = localStorage.getItem(LS_CURRENT_STEP_KEY);

            if (savedFormState) formState = JSON.parse(savedFormState); else formState = {};
            if (savedSubmissions) submissions = JSON.parse(savedSubmissions); else submissions = [];
            
            if (formState.hasRelatedProcesses === undefined) formState.hasRelatedProcesses = null;
            if (!Array.isArray(formState.relatedProcessesArray)) formState.relatedProcessesArray = [];

            if (savedCurrentStep) currentStep = parseInt(savedCurrentStep, 10); else currentStep = 0;
            
            if (isNaN(currentStep) || currentStep < 0 || currentStep >= stepsData.length) {
                currentStep = 0;
            }
            console.log('Loaded from LocalStorage: currentStep:', currentStep, 'formState:', JSON.parse(JSON.stringify(formState)), 'submissions:', submissions.length);
            if(formState.organization_type) {
                console.log('organization_type from localStorage:', formState.organization_type);
            }
        }
        */

        function saveStateToLocalStorage() {
            localStorage.setItem(LS_FORM_STATE_KEY, JSON.stringify(formState));
            localStorage.setItem(LS_SUBMISSIONS_KEY, JSON.stringify(submissions));
            localStorage.setItem(LS_CURRENT_STEP_KEY, currentStep.toString());
        }

        function clearLocalStorageAndReset() {
            if (confirm("Вы уверены, что хотите удалить все введенные данные и начать заново? Это действие необратимо.")) {
                localStorage.removeItem(LS_FORM_STATE_KEY);
                localStorage.removeItem(LS_SUBMISSIONS_KEY);
                localStorage.removeItem(LS_CURRENT_STEP_KEY);
                
                currentStep = STEP_GLOSSARY; 
                formState = { hasRelatedProcesses: null, relatedProcessesArray: [] }; 
                submissions = []; 
                
                console.log('State reset by button: currentStep:', currentStep, 'formState:', JSON.parse(JSON.stringify(formState)));
                
                showToast("Все данные очищены. Начните сначала.", "info");
                emailBlock.classList.add('hidden');
                renderAll(); 
                updateCounter();
            }
        }

        function applySavedTheme() {
            const savedTheme = localStorage.getItem(LS_THEME_KEY);
            const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
            const useDark = savedTheme === 'dark' || (!savedTheme && prefersDark);
            htmlEl.classList.toggle('dark', useDark);
            themeToggle.textContent = useDark ? '☀️' : '🌙';
        }
        function toggleTheme() {
            const isDark = htmlEl.classList.toggle('dark');
            themeToggle.textContent = isDark ? '☀️' : '🌙';
            localStorage.setItem(LS_THEME_KEY, isDark ? 'dark' : 'light');
        }
        function handleGlobalKeyDown(event) {
            if (event.key === 'Escape') {
                const activeElement = document.activeElement;
                if (activeElement && activeElement.dataset.fieldIdForTip) {
                    toggleTip(activeElement.dataset.fieldIdForTip, false);
                } else { 
                    const openTooltips = document.querySelectorAll('[id^="tip-"]:not(.hidden)');
                    openTooltips.forEach(tip => {
                        const fieldId = tip.id.substring(4); 
                        toggleTip(fieldId, false);
                    });
                }
            }
        }
        
        function handleAppliedTechCheckboxChange(event) {
            console.log('handleAppliedTechCheckboxChange triggered by:', event.target.name, event.target.value, event.target.checked);
            if (event.target.type !== 'checkbox') return;

            const changedCheckbox = event.target;
            const fieldName = changedCheckbox.name; 
            const changedValue = changedCheckbox.value; 
            const isChecked = changedCheckbox.checked; 
            const notAppliedValue = "Не применяются"; 

            if (fieldName === 'applied_tech') {
                const groupContainer = changedCheckbox.closest('div[id$="-checkbox-group"]'); 
                if (!groupContainer) {
                    console.error('Checkbox group container not found for applied_tech');
                    return; 
                }
                const allCheckboxes = groupContainer.querySelectorAll('input[type="checkbox"]');

                if (changedValue === notAppliedValue) {
                    if (isChecked) {
                        allCheckboxes.forEach(cb => {
                            if (cb !== changedCheckbox) {
                                cb.checked = false; 
                                cb.disabled = true; 
                            } else {
                                cb.disabled = false; 
                            }
                            const label = cb.closest('label');
                            if(label) {
                                label.classList.toggle('opacity-50', cb.disabled);
                                label.classList.toggle('cursor-not-allowed', cb.disabled);
                            }
                        });
                        formState[fieldName] = [notAppliedValue];
                    } else {
                        allCheckboxes.forEach(cb => {
                            cb.disabled = false;
                            const label = cb.closest('label');
                            if(label) label.classList.remove('opacity-50', 'cursor-not-allowed');
                        });
                        formState[fieldName] = (formState[fieldName] || []).filter(item => item !== notAppliedValue);
                    }
                } else { 
                    if (isChecked) {
                        allCheckboxes.forEach(cb => {
                            if (cb.value === notAppliedValue) {
                                cb.checked = false;
                                cb.disabled = true;
                            } else {
                                cb.disabled = false; 
                            }
                            const label = cb.closest('label');
                            if(label) {
                                label.classList.toggle('opacity-50', cb.disabled);
                                label.classList.toggle('cursor-not-allowed', cb.disabled);
                            }
                        });
                        let currentSelection = (formState[fieldName] || []).filter(item => item !== notAppliedValue);
                        if (!currentSelection.includes(changedValue)) {
                            currentSelection.push(changedValue);
                        }
                        formState[fieldName] = currentSelection;
                    } else {
                        formState[fieldName] = (formState[fieldName] || []).filter(item => item !== changedValue);
                        const anyOtherTechChecked = (formState[fieldName] || []).length > 0; 
                        allCheckboxes.forEach(cb => {
                            if (cb.value === notAppliedValue) {
                                cb.disabled = anyOtherTechChecked;
                                const label = cb.closest('label');
                                if(label) {
                                    label.classList.toggle('opacity-50', cb.disabled);
                                    label.classList.toggle('cursor-not-allowed', cb.disabled);
                                }
                            }
                        });
                    }
                }
                console.log('formState[applied_tech] after change:', formState[fieldName]);
                updateNav();
                saveStateToLocalStorage(); 
            } else { 
                console.warn('handleAppliedTechCheckboxChange called for unexpected fieldName:', fieldName);
                updateFormStateForGenericCheckbox(fieldName, changedValue, isChecked);
                updateNav();
                saveStateToLocalStorage(); 
            }
        }

        function updateFormStateForGenericCheckbox(fieldName, value, isChecked) {
            console.log('updateFormStateForGenericCheckbox:', fieldName, value, isChecked);
            if (!formState[fieldName] || !Array.isArray(formState[fieldName])) {
                formState[fieldName] = [];
            }
            if (isChecked) {
                if (!formState[fieldName].includes(value)) formState[fieldName].push(value);
            } else {
                formState[fieldName] = formState[fieldName].filter(item => item !== value);
            }
        }

        function handleKpiChange() {
            if (currentStep !== STEP_DOCS_RESULTS_KPI) return;
            const kpiExistsSelect = document.getElementById('kpi_exists');
            const kpiDetailsContainer = document.getElementById('container-kpi_details');
            if (!kpiExistsSelect || !kpiDetailsContainer) {
                console.warn('KPI elements not found for handleKpiChange');
                return;
            }
            const selectedValue = kpiExistsSelect.value;
            const kpiDetailsInput = document.getElementById('kpi_details');
            console.log('handleKpiChange - selectedValue:', selectedValue);
            if (selectedValue === "Да") {
                kpiDetailsContainer.classList.remove('hidden');
            } else {
                kpiDetailsContainer.classList.add('hidden');
                if (kpiDetailsInput) kpiDetailsInput.value = '';
                delete formState['kpi_details'];
            }
            updateNav();
            saveStateToLocalStorage(); 
        }

        function handleOrganizationChange() {
            console.log('handleOrganizationChange called. Current step:', currentStep);
            if (currentStep !== STEP_PROCESS_MAIN_INFO) {
                console.log('handleOrganizationChange: Not on STEP_PROCESS_MAIN_INFO, returning.');
                return;
            }

            const orgTypeSelect = document.getElementById('organization_type');
            const regionalAuthorityContainer = document.getElementById('container-regional_authority_name');
            const subordinateOrgContainer = document.getElementById('container-subordinate_org_name');

            console.log('orgTypeSelect:', orgTypeSelect);
            console.log('regionalAuthorityContainer:', regionalAuthorityContainer);
            console.log('subordinateOrgContainer:', subordinateOrgContainer);

            if (!orgTypeSelect || !regionalAuthorityContainer || !subordinateOrgContainer) {
                console.error('One or more elements for organization change not found!');
                return;
            }

            const selectedValue = orgTypeSelect.value;
            console.log('Selected organization_type value:', `"${selectedValue}"`); 

            const regionalAuthorityInput = document.getElementById('regional_authority_name');
            const subordinateOrgInput = document.getElementById('subordinate_org_name');

            if (selectedValue === "Региональный орган власти") {
                console.log('Condition: selectedValue === "Региональный орган власти" is TRUE');
                regionalAuthorityContainer.classList.remove('hidden'); 
                subordinateOrgContainer.classList.add('hidden');    
                if (subordinateOrgInput) subordinateOrgInput.value = ''; 
                delete formState['subordinate_org_name']; 
            } else if (selectedValue === "Подведомственная организация") {
                console.log('Condition: selectedValue === "Подведомственная организация" is TRUE');
                regionalAuthorityContainer.classList.remove('hidden'); 
                subordinateOrgContainer.classList.remove('hidden'); 
            } else {
                console.log('Condition: No specific organization type selected (or empty value)');
                regionalAuthorityContainer.classList.add('hidden');    
                subordinateOrgContainer.classList.add('hidden');    
                if (regionalAuthorityInput) regionalAuthorityInput.value = '';
                if (subordinateOrgInput) subordinateOrgInput.value = '';
                delete formState['regional_authority_name'];
                delete formState['subordinate_org_name'];
            }
            console.log('regional_authority_name hidden:', regionalAuthorityContainer.classList.contains('hidden'));
            console.log('subordinate_org_name hidden:', subordinateOrgContainer.classList.contains('hidden'));
            updateNav();
            saveStateToLocalStorage(); 
        }


        function renderProgress() {
            progressBar.innerHTML = stepsData.map((step, i) => {
                const isDone = i < currentStep;
                const isCurrent = i === currentStep;
                let lineStateClass = isDone ? 'border-primary dark:border-accent' : 'border-gray-300 dark:border-gray-700';
                const iconBaseClasses = 'w-8 h-8 md:w-10 md:h-10 flex-shrink-0 flex items-center justify-center rounded-full text-sm font-medium transition-all duration-300 border-2';
                let iconStateClasses = 'bg-card dark:bg-gray-800 border-gray-400 dark:border-gray-600 text-gray-400 dark:text-gray-500';
                if (isCurrent) iconStateClasses = 'bg-accent text-white border-accent';
                else if (isDone) iconStateClasses = 'bg-primary text-white border-primary';
                const connectorHtml = (i < stepsData.length - 1) ? `<div class="flex-grow border-t-2 ${lineStateClass} self-center mx-1 transition-colors duration-300"></div>` : '';
                return `<span title="${step.title}" class="${iconBaseClasses} ${iconStateClasses}">${step.icon || (i + 1)}</span>${connectorHtml}`;
            }).join('');
        }
        function createFieldTooltipHtml(fieldId, fieldLabel, tooltipText) {
            if (!tooltipText) return '';
            return `
                <button type="button" aria-label="Подсказка для ${fieldLabel}" 
                        data-field-id-for-tip="${fieldId}" 
                        onclick="toggleTip(this.dataset.fieldIdForTip, true)" 
                        onblur="setTimeout(() => toggleTip(this.dataset.fieldIdForTip, false), 100)" 
                        class="absolute top-0 right-0 mt-1 text-gray-400 hover:text-primary dark:hover:text-blue-400 focus:outline-none focus:ring-2 focus:ring-offset-1 focus:ring-accent rounded-full p-0.5">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd" /></svg>
                </button>
                <div id="tip-${fieldId}" class="absolute top-full left-0 mt-1 p-3 bg-tooltip dark:bg-gray-700 rounded-xl2 text-sm text-gray-700 dark:text-gray-200 shadow-lg hidden z-20 max-w-xs border border-gray-200 dark:border-gray-600" role="tooltip" aria-hidden="true">
                    ${tooltipText}
                </div>`;
        }

        function renderStep() {
            console.log(`renderStep called for step: ${currentStep} - ${stepsData[currentStep]?.title}`);
            if (currentStep < 0 || currentStep >= stepsData.length) currentStep = 0;
            const stepConfig = stepsData[currentStep];
            const { title, fields, stepDefinitionHtml, customRenderFunctionName, maxRelatedProcesses } = stepConfig;
            stepTitleEl.textContent = title;
            stepDefinitionContainer.innerHTML = ''; 
            formSteps.innerHTML = ''; 
            if (stepDefinitionHtml) {
                const definitionElement = document.createElement('div');
                definitionElement.id = 'stepDefinitionContent';
                definitionElement.className = 'p-4 mb-6 bg-gray-50 dark:bg-gray-950 border border-gray-200 dark:border-gray-600 rounded-xl2 shadow-soft text-sm text-gray-700 dark:text-gray-300';
                definitionElement.innerHTML = stepDefinitionHtml;
                stepDefinitionContainer.appendChild(definitionElement);
            }
            if (customRenderFunctionName && typeof window[customRenderFunctionName] === 'function') {
                console.log(`Calling custom render function: ${customRenderFunctionName}`);
                window[customRenderFunctionName](formSteps, maxRelatedProcesses);
            } else if (fields && fields.length > 0) {
                formSteps.innerHTML = fields.map(f => {
                    if (!f || !f.id) return '';
                    const isConditional = f.conditional;
                    const hiddenClass = isConditional ? 'hidden' : '';
                    const wrapperTag = f.type === 'checkboxGroup' ? 'fieldset' : 'div';
                    const wrapperStart = `<${wrapperTag} id="container-${f.id}" class="flex flex-col relative space-y-1 ${hiddenClass}">`;
                    const wrapperEnd = `</${wrapperTag}>`;
                    let fieldHtml = '';
                    const value = formState[f.id] || (f.type === 'checkboxGroup' ? [] : ''); 
                    const commonInputClasses = "p-2.5 border border-gray-300 dark:border-gray-600 rounded-xl2 focus:ring-2 focus:ring-offset-0 focus:ring-primary focus:border-primary dark:focus:border-primary bg-card dark:bg-gray-800 dark:text-gray-100 w-full transition-shadow duration-150 ease-in-out shadow-sm hover:shadow-md focus:shadow-lg";
                    const labelClasses = "font-medium text-gray-700 dark:text-gray-300";
                    if (f.type === 'checkboxGroup') {
                        const checkboxesHtml = (f.options || []).map((option, index) => {
                        const checkboxId = `${f.id}-${index}`;
                        const currentValueArray = Array.isArray(value) ? value : []; 
                        const notAppliedValue = "Не применяются";
                        const fieldName = f.id; 

                        let isChecked = currentValueArray.includes(option);
                        let isDisabled = false;
                        
                        if (fieldName === 'applied_tech') { 
                            const isNotAppliedSelected = currentValueArray.includes(notAppliedValue);
                            const anyTechSelected = currentValueArray.some(item => item !== notAppliedValue);

                            if (option === notAppliedValue) {
                                isDisabled = anyTechSelected; 
                            } else {
                                isDisabled = isNotAppliedSelected; 
                            }
                            if(isDisabled) isChecked = false; 
                        } 

                        const checkboxLabelClasses = `flex items-center space-x-2 cursor-pointer text-sm text-gray-700 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-700 p-2 rounded-md ${isDisabled ? 'opacity-50 cursor-not-allowed' : ''}`;
                        const inputClasses = `rounded border-gray-300 dark:border-gray-600 text-primary shadow-sm focus:ring-offset-0 focus:ring-primary/50 dark:bg-gray-700 ${isDisabled ? 'cursor-not-allowed' : ''}`;

                        return `
                                <label for="${checkboxId}" class="${checkboxLabelClasses}">
                                    <input type="checkbox" id="${checkboxId}" name="${f.id}" value="${option}"
                                           class="${inputClasses}"
                                           ${isChecked ? 'checked' : ''}
                                           ${isDisabled ? 'disabled' : ''}>
                                    <span>${option}</span>
                                </label>`;
                        }).join('');
                            fieldHtml = `<legend class="${labelClasses} mb-1">${f.label}</legend><div id="${f.id}-checkbox-group" class="relative mt-1 space-y-1 border border-gray-200 dark:border-gray-700 p-3 rounded-xl2 shadow-sm">${checkboxesHtml}</div>${createFieldTooltipHtml(f.id, f.label, f.tooltip)}`;
                    } else if (f.type === 'select') {
                            fieldHtml = `<label for="${f.id}" class="${labelClasses}">${f.label}</label><select id="${f.id}" name="${f.id}" aria-describedby="tip-${f.id}" class="${commonInputClasses} appearance-none"><option value="">-- Выберите --</option>${(f.options || []).map(o => `<option value="${o}" ${value === o ? 'selected' : ''}>${o}</option>`).join('')}</select>${createFieldTooltipHtml(f.id, f.label, f.tooltip)}`;
                    } else { 
                            fieldHtml = `<label for="${f.id}" class="${labelClasses}">${f.label}</label><input id="${f.id}" name="${f.id}" type="${f.type || 'text'}" placeholder="${f.placeholder || ''}" value="${value}" ${(f.type ==='number' && f.min !== undefined) ? `min="${f.min}"` : ''} aria-describedby="tip-${f.id}" class="${commonInputClasses}"/>${createFieldTooltipHtml(f.id, f.label, f.tooltip)}`;
                    }
                    return wrapperStart + fieldHtml + wrapperEnd;
                }).join('');
                fields.forEach(f => {
                    if (!f || !f.id) return;
                    const el = document.getElementById(f.id);
                    if (f.type === 'checkboxGroup') {
                        const groupContainer = document.getElementById(`${f.id}-checkbox-group`);
                        if (groupContainer) {
                            if (f.id === 'applied_tech') {
                                console.log(`Attaching handleAppliedTechCheckboxChange to checkbox group: ${f.id}`);
                                groupContainer.addEventListener('change', handleAppliedTechCheckboxChange);
                            }
                        }
                    } else if (el) {
                        const eventType = (el.tagName === 'SELECT' || f.type === 'checkbox') ? 'change' : 'input';
                        el.addEventListener(eventType, onInput);
                        if (f.type === 'number') el.addEventListener('blur', validateNumericInputOnBlur);
                        
                        if (f.id === 'organization_type' && currentStep === STEP_PROCESS_MAIN_INFO) {
                            console.log('Attaching change listener to organization_type select:', el);
                            el.addEventListener('change', handleOrganizationChange);
                        }
                        if (f.id === 'kpi_exists' && currentStep === STEP_DOCS_RESULTS_KPI) {
                             console.log('Attaching change listener to kpi_exists select:', el);
                            el.addEventListener('change', handleKpiChange);
                        }
                    }
                });
            } else {
                if(!stepDefinitionHtml && !(customRenderFunctionName && typeof window[customRenderFunctionName] === 'function')) {
                    formSteps.innerHTML = '';
                }
            }

            if (currentStep === STEP_PROCESS_MAIN_INFO) {
                console.log('renderStep: Calling handleOrganizationChange for initial setup of STEP_PROCESS_MAIN_INFO.');
                handleOrganizationChange();
            }
            if (currentStep === STEP_DOCS_RESULTS_KPI) {
                console.log('renderStep: Calling handleKpiChange for initial setup of STEP_DOCS_RESULTS_KPI.');
                handleKpiChange();
            }
            updateNav(); 
        }
        
        function renderRelatedProcessesStepControls(container, maxProcesses) {
            console.log('renderRelatedProcessesStepControls called');
            container.innerHTML = ''; 
            if (formState.hasRelatedProcesses === undefined) formState.hasRelatedProcesses = null;
            if (!Array.isArray(formState.relatedProcessesArray)) formState.relatedProcessesArray = [];
            const docFragment = document.createDocumentFragment();
            const questionSection = document.createElement('div');
            questionSection.className = 'mb-6 p-4 border border-gray-200 dark:border-gray-700 rounded-xl2 shadow-sm';
            const questionP = document.createElement('p');
            questionP.className = 'font-medium text-gray-700 dark:text-gray-300 mb-3';
            questionP.textContent = 'Есть ли у описываемого процесса связанные процессы?';
            questionSection.appendChild(questionP);
            const radioGroup = document.createElement('div');
            radioGroup.className = 'flex items-center space-x-6';
            ['yes', 'no'].forEach(value => {
                const wrapper = document.createElement('div');
                wrapper.className = 'flex items-center';
                const radioInput = document.createElement('input');
                radioInput.type = 'radio';
                radioInput.name = 'hasRelatedProcessesRadio';
                radioInput.id = `hasRelated_${value}`;
                radioInput.value = value;
                radioInput.checked = formState.hasRelatedProcesses === value;
                radioInput.className = 'h-4 w-4 text-primary border-gray-300 focus:ring-primary dark:bg-gray-700 dark:border-gray-600';
                radioInput.addEventListener('change', (e) => {
                    console.log('Related processes radio changed:', e.target.value);
                    formState.hasRelatedProcesses = e.target.value;
                    if (e.target.value === 'yes' && formState.relatedProcessesArray.length === 0) {
                        formState.relatedProcessesArray.push('');
                    }
                    renderRelatedProcessesStepControls(container, maxProcesses);
                    updateNav();
                    saveStateToLocalStorage(); 
                });
                const radioLabel = document.createElement('label');
                radioLabel.htmlFor = `hasRelated_${value}`;
                radioLabel.textContent = value === 'yes' ? 'Да, есть' : 'Нет';
                radioLabel.className = 'ml-2 text-sm font-medium text-gray-700 dark:text-gray-300 cursor-pointer';
                wrapper.appendChild(radioInput);
                wrapper.appendChild(radioLabel);
                radioGroup.appendChild(wrapper);
            });
            questionSection.appendChild(radioGroup);
            docFragment.appendChild(questionSection);

            if (formState.hasRelatedProcesses === 'yes') {
                const processesListSection = document.createElement('div');
                processesListSection.id = 'related-processes-inputs-container';
                processesListSection.className = 'space-y-3 mt-4';
                formState.relatedProcessesArray.forEach((processText, index) => {
                    const fieldWrapper = document.createElement('div');
                    fieldWrapper.className = 'flex items-center space-x-2';
                    const input = document.createElement('input');
                    input.type = 'text';
                    input.placeholder = `Наименование связанного процесса ${index + 1}`;
                    input.value = processText;
                    input.className = "flex-grow p-2.5 border border-gray-300 dark:border-gray-600 rounded-xl2 focus:ring-2 focus:ring-primary bg-card dark:bg-gray-800 dark:text-gray-100 shadow-sm";
                    input.dataset.index = index;
                    input.addEventListener('input', (e) => {
                        formState.relatedProcessesArray[index] = e.target.value;
                        updateNav(); 
                        saveStateToLocalStorage(); 
                    });
                    const deleteBtn = document.createElement('button');
                    deleteBtn.type = 'button';
                    deleteBtn.setAttribute('aria-label', `Удалить процесс ${index + 1}`);
                    deleteBtn.title = `Удалить процесс ${index + 1}`;
                    deleteBtn.className = 'p-2 text-red-500 hover:text-red-700 hover:bg-red-100 dark:hover:bg-red-900/50 rounded-full transition-colors';
                    deleteBtn.innerHTML = `<svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M9 2a1 1 0 00-.894.553L7.382 4H4a1 1 0 000 2v10a2 2 0 002 2h8a2 2 0 002-2V6a1 1 0 100-2h-3.382l-.724-1.447A1 1 0 0011 2H9zM7 8a1 1 0 012 0v6a1 1 0 11-2 0V8zm5-1a1 1 0 00-1 1v6a1 1 0 102 0V8a1 1 0 00-1-1z" clip-rule="evenodd"></path></svg>`;
                    deleteBtn.addEventListener('click', () => {
                        formState.relatedProcessesArray.splice(index, 1);
                        if (formState.relatedProcessesArray.length === 0 && formState.hasRelatedProcesses === 'yes') {
                            formState.relatedProcessesArray.push(''); 
                        }
                        renderRelatedProcessesStepControls(container, maxProcesses);
                        updateNav();
                        saveStateToLocalStorage(); 
                    });
                    fieldWrapper.appendChild(input);
                    fieldWrapper.appendChild(deleteBtn);
                    processesListSection.appendChild(fieldWrapper);
                });
                docFragment.appendChild(processesListSection);

                if (formState.relatedProcessesArray.length < maxProcesses) {
                    const addButton = document.createElement('button');
                    addButton.type = 'button';
                    addButton.textContent = '+ Добавить еще процесс';
                    addButton.className = 'mt-4 px-4 py-2 text-sm bg-green-500 hover:bg-green-600 text-white rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-green-400 focus:ring-offset-2';
                    addButton.addEventListener('click', () => {
                        if (formState.relatedProcessesArray.length < maxProcesses) {
                            formState.relatedProcessesArray.push('');
                            renderRelatedProcessesStepControls(container, maxProcesses);
                            const listContainer = document.getElementById('related-processes-inputs-container');
                            if (listContainer) {
                                const inputs = listContainer.querySelectorAll('input[type="text"]');
                                if (inputs.length > 0) inputs[inputs.length - 1].focus();
                            }
                            updateNav();
                            saveStateToLocalStorage(); 
                        }
                    });
                    docFragment.appendChild(addButton);
                }
            }
            container.appendChild(docFragment);
        }

        function validateNumericInputOnBlur(event) {
            const el = event.target;
            if (el.type === 'number') validateSingleField(el.id, el.value);
        }

        function validateSingleField(fieldId, value) {
            const fieldConfig = stepsData[currentStep]?.fields.find(f => f.id === fieldId);
            const el = document.getElementById(fieldId);
            const labelEl = document.querySelector(`label[for='${fieldId}']`) || document.querySelector(`#container-${fieldId} legend`);
            if (!fieldConfig || (!el && fieldConfig.type !== 'checkboxGroup')) return {isValid: true}; 
            let isValid = true;
            const container = document.getElementById(`container-${fieldId}`);
            if (!container || !container.classList.contains('hidden')) {
                if (fieldConfig.type === 'checkboxGroup') {
                    isValid = Array.isArray(value) && value.length > 0;
                } else if (String(value).trim() === '') {
                    isValid = false;
                }
            }
            if (isValid && fieldConfig.type === 'number' && String(value).trim() !== '') {
                const numValue = parseFloat(value);
                const min = parseFloat(fieldConfig.min);
                if (isNaN(numValue)) {
                    isValid = false;
                } else if (min !== undefined && numValue < min) {
                    isValid = false;
                }
            }
            const targetElForError = el || (fieldConfig.type === 'checkboxGroup' ? document.getElementById(`${fieldId}-checkbox-group`) : null);
            if (targetElForError) targetElForError.classList.toggle('field-error', !isValid);
            if (labelEl) labelEl.classList.toggle('label-error', !isValid);
            return {isValid, fieldConfig}; 
        }

        function onInput(e) {
            const fieldId = e.target.id;
            let value = e.target.value;
            console.log(`onInput for fieldId: ${fieldId}, value: "${value}"`);

            const fieldConfig = stepsData[currentStep]?.fields.find(f => f.id === fieldId);
            if (fieldConfig) {
                formState[fieldId] = value; 
                const el = document.getElementById(fieldId);
                const labelEl = document.querySelector(`label[for='${fieldId}']`);
                if (el) el.classList.remove('field-error');
                if (labelEl) labelEl.classList.remove('label-error');
            } else {
                 console.warn(`onInput: No fieldConfig found for fieldId: ${fieldId}`);
            }
            updateNav();
            saveStateToLocalStorage(); 
        }
        
        function updateNav() {
            if (currentStep < 0 || currentStep >= stepsData.length) {
                console.warn('updateNav: currentStep is out of bounds:', currentStep);
                return;
            }
            const stepConfig = stepsData[currentStep];
            let isStepCurrentlyValid = true;

            if (stepConfig.customRenderFunctionName === 'renderRelatedProcessesStepControls' && currentStep === STEP_RELATED_PROCESSES) {
                if (formState.hasRelatedProcesses === null) {
                    isStepCurrentlyValid = false;
                } else if (formState.hasRelatedProcesses === 'yes') {
                    isStepCurrentlyValid = Array.isArray(formState.relatedProcessesArray) &&
                                           formState.relatedProcessesArray.length > 0 &&
                                           formState.relatedProcessesArray.some(proc => proc && proc.trim() !== '');
                } else { 
                    isStepCurrentlyValid = true;
                }
                 console.log('updateNav (Related Processes): isStepCurrentlyValid:', isStepCurrentlyValid, 'formState.hasRelatedProcesses:', formState.hasRelatedProcesses);
            } else if (stepConfig.fields && stepConfig.fields.length > 0) {
                for (const f of stepConfig.fields) {
                    const container = document.getElementById(`container-${f.id}`);
                    if (container && container.classList.contains('hidden')) continue;
                    const fieldElement = document.getElementById(f.id);
                    const valueToValidate = f.type === 'checkboxGroup' 
                        ? (formState[f.id] || []) 
                        : (fieldElement ? fieldElement.value : (formState[f.id] || ''));
                    
                    const { isValid } = validateSingleField(f.id, valueToValidate);
                    if (!isValid) { 
                        isStepCurrentlyValid = false; 
                        break; 
                    }
                }
            } else {
                isStepCurrentlyValid = true; 
            }
            
            nextBtn.disabled = !isStepCurrentlyValid;
            nextBtn.classList.toggle('opacity-50', !isStepCurrentlyValid);
            nextBtn.classList.toggle('cursor-not-allowed', !isStepCurrentlyValid);

            const isLastDataEntryStep = currentStep === STEP_WORKFLOW_TECH;
            if (isLastDataEntryStep) {
                nextBtn.textContent = 'Добавить процесс';
                const canExport = submissions.length > 0 || (isStepCurrentlyValid && formHasAnyData(formState));
                exportBtn.classList.toggle('hidden', !canExport);
            } else {
                nextBtn.textContent = 'Далее →';
                exportBtn.classList.add('hidden');
            }
            prevBtn.disabled = currentStep === 0;
            prevBtn.classList.toggle('opacity-50', currentStep === 0);
            prevBtn.classList.toggle('cursor-not-allowed', currentStep === 0);
        }

        window.toggleTip = function(fieldId, show) {
            const tipElement = document.getElementById(`tip-${fieldId}`);
            const buttonEl = document.querySelector(`button[data-field-id-for-tip="${fieldId}"]`);
            if (tipElement) {
                tipElement.classList.toggle('hidden', !show);
                tipElement.setAttribute('aria-hidden', String(!show));
                if (show && buttonEl) buttonEl.focus();
            }
        }
        function saveCurrentStepDataToFormState() {
            console.log('saveCurrentStepDataToFormState called for step:', currentStep);
            const fields = stepsData[currentStep]?.fields;
            if (fields && fields.length > 0) { 
                fields.forEach(f => {
                    if (!f || !f.id) return;
                    const el = document.getElementById(f.id);
                    const container = document.getElementById(`container-${f.id}`);
                    if (container && container.classList.contains('hidden')) {
                        console.log(`Field ${f.id} is hidden, deleting from formState.`);
                        delete formState[f.id]; return;
                    }
                    if (f.type === 'checkboxGroup') { 
                        if (!formState[f.id]) formState[f.id] = []; 
                    }
                    else if (el) { 
                        formState[f.id] = el.value; 
                    }
                });
            }
             console.log('FormState after saveCurrentStepDataToFormState:', JSON.parse(JSON.stringify(formState)));
        }
        function handlePrevClick() {
            console.log('handlePrevClick. Current step before:', currentStep);
            if (currentStep === STEP_RELATED_PROCESSES) { 
                console.log('Prev on Related Processes step, data should be in formState.');
            }
            else { saveCurrentStepDataToFormState(); } 
            if (currentStep > 0) { currentStep--; renderAll(); }
        }

        function handleNextClickOrAddProcess() {
            console.log('handleNextClickOrAddProcess. Current step:', currentStep);
            if (currentStep === STEP_RELATED_PROCESSES) {
                if (formState.hasRelatedProcesses === 'yes' && Array.isArray(formState.relatedProcessesArray)) {
                    formState.relatedProcessesArray = formState.relatedProcessesArray.filter(proc => proc && proc.trim() !== '');
                } else if (formState.hasRelatedProcesses === 'no') {
                    formState.relatedProcessesArray = [];
                } else if (formState.hasRelatedProcesses === null) {
                    showToast('Пожалуйста, укажите, есть ли связанные процессы.', 'warning');
                     console.log('Next click on Related: hasRelatedProcesses is null.');
                    return; 
                }
            } else {
                saveCurrentStepDataToFormState(); 
            }

            updateNav(); 
            if (nextBtn.disabled) { 
                console.log('Next button is disabled. Validation failed.');
                const stepConfig = stepsData[currentStep];
                if (stepConfig.customRenderFunctionName === 'renderRelatedProcessesStepControls' && currentStep === STEP_RELATED_PROCESSES) {
                    if(formState.hasRelatedProcesses === null) showToast('Пожалуйста, укажите, есть ли связанные процессы.', 'warning');
                    else if(formState.hasRelatedProcesses === 'yes') showToast('Пожалуйста, корректно заполните информацию о связанных процессах (хотя бы один).', 'warning');
                } else if (stepConfig.fields && stepConfig.fields.length > 0) {
                    let firstInvalidField = null;
                    for (const f of stepConfig.fields) {
                        const container = document.getElementById(`container-${f.id}`);
                        if (container && container.classList.contains('hidden')) continue;
                        const fieldElement = document.getElementById(f.id);
                        const valueToValidate = f.type === 'checkboxGroup' ? (formState[f.id] || []) : (fieldElement ? fieldElement.value : (formState[f.id] || ''));
                        const { isValid, fieldConfig: cfg } = validateSingleField(f.id, valueToValidate);
                        if(!isValid) { firstInvalidField = cfg; break; }
                    }
                    if(firstInvalidField) showToast(`Пожалуйста, заполните поле «${firstInvalidField.label}» корректно.`, "warning");
                    else showToast('Пожалуйста, заполните все обязательные поля корректно.', 'warning');
                }
                return;
            }
            console.log('Next button is enabled. Proceeding.');

            if (currentStep < STEP_WORKFLOW_TECH) {
                currentStep++;
                renderAll();
            } else { 
                setButtonLoadingState(nextBtn, true, "Добавление...");
                setTimeout(() => { 
                    addProcess();
                    setButtonLoadingState(nextBtn, false, "Добавить процесс");
                }, 200);
            }
        }
        
        function formHasAnyData(dataObject) {
             if (!dataObject || typeof dataObject !== 'object') return false;
             const keys = Object.keys(dataObject);
             if (keys.length === 0) return false;
             let significantKeyCount = 0;
             for (const key in dataObject) {
                 if (key === 'hasRelatedProcesses') continue;
                 if (key === 'relatedProcessesArray' && (!Array.isArray(dataObject[key]) || dataObject[key].filter(p=>p.trim()!=='').length === 0)) continue;
                 if (key === 'region' && !dataObject[key]) continue;
                 if (key === 'fio' && !dataObject[key]) continue;
                 const value = dataObject[key];
                 if ((typeof value === 'string' && value.trim() !== '') ||
                     (typeof value === 'number' && !isNaN(value)) ||
                     (Array.isArray(value) && value.length > 0 && !(key === 'relatedProcessesArray' && value.filter(p=>p.trim()!=='').length === 0) )) { 
                     significantKeyCount++;
                 }
             }
             const hasData = significantKeyCount > 0;
             console.log('formHasAnyData result:', hasData, 'Significant keys:', significantKeyCount);
             return hasData;
        }
        
        function addProcess() {
            console.log('addProcess called. Current formState:', JSON.parse(JSON.stringify(formState)));
            if (formState.hasRelatedProcesses === 'yes' && Array.isArray(formState.relatedProcessesArray)) {
                formState.relatedProcessesArray = formState.relatedProcessesArray.filter(proc => proc && proc.trim() !== '');
                if (formState.relatedProcessesArray.length === 0) {
                    showToast('Невозможно добавить процесс: если указано наличие связанных процессов, необходимо заполнить хотя бы один.', 'warning');
                    return;
                }
            } else if (formState.hasRelatedProcesses === 'no' || formState.hasRelatedProcesses === null) {
                formState.relatedProcessesArray = [];
            }

            if (!formHasAnyData(formState)) {
                showToast("Нет данных для добавления. Заполните хотя бы одно поле процесса, кроме региона и ФИО.", "warning");
                return;
            }

            const processDataToAdd = { ...formState }; 
            if (!Array.isArray(processDataToAdd.relatedProcessesArray)) {
                processDataToAdd.relatedProcessesArray = [];
            }

            submissions.push(processDataToAdd);
            showToast(`Процесс "${processDataToAdd.process_name || 'Без названия'}" добавлен (${submissions.length})`, 'success');
            console.log('Process added. Submissions count:', submissions.length);

            const personalDataToKeep = {};
            if (stepsData[STEP_PERSONAL_DATA]?.fields) {
                stepsData[STEP_PERSONAL_DATA].fields.forEach(field => {
                    if (field?.id && processDataToAdd.hasOwnProperty(field.id)) {
                        personalDataToKeep[field.id] = processDataToAdd[field.id];
                    }
                });
            }
            formState = { ...personalDataToKeep, hasRelatedProcesses: null, relatedProcessesArray: [] }; 
            currentStep = (personalDataToKeep.region && personalDataToKeep.fio) ? STEP_PROCESS_MAIN_INFO : STEP_PERSONAL_DATA;
            console.log('Form state reset for new process. New currentStep:', currentStep, 'Kept personal data:', personalDataToKeep);
            emailBlock.classList.add('hidden');
            renderAll();
            // updateCounter();
            saveStateToLocalStorage(); 
        }

        function setButtonLoadingState(button, isLoading, loadingText = "Загрузка...") {
            if (!button) return;
            if (isLoading) {
                button.disabled = true;
                button.dataset.originalText = button.textContent;
                button.innerHTML = loadingText; 
                button.classList.add('button-loading');
            } else {
                button.disabled = false;
                button.innerHTML = button.dataset.originalText || "Далее →";
                button.classList.remove('button-loading');
            }
        }
        function exportToExcelHandler() {
            setButtonLoadingState(exportBtn, true, "Экспорт...");
            setTimeout(() => { 
                exportToExcel();
                const originalText = exportBtn.dataset.originalText || "Экспорт в Excel";
                setButtonLoadingState(exportBtn, false, originalText);
            }, 200);
        }

        function exportToExcel() {
            console.log('exportToExcel called. Current step:', currentStep);
             if (currentStep !== STEP_RELATED_PROCESSES && stepsData[currentStep].fields && stepsData[currentStep].fields.length > 0){
                saveCurrentStepDataToFormState(); 
            } else if (currentStep === STEP_RELATED_PROCESSES) {
                 if (formState.hasRelatedProcesses === 'yes' && Array.isArray(formState.relatedProcessesArray)) {
                    formState.relatedProcessesArray = formState.relatedProcessesArray.filter(proc => proc && proc.trim() !== '');
                } else if (formState.hasRelatedProcesses === 'no' || formState.hasRelatedProcesses === null) {
                    formState.relatedProcessesArray = [];
                }
            }
            console.log('Form state before preparing export:', JSON.parse(JSON.stringify(formState)));

            const recordsToExport = [...submissions];
            let currentFormCanBeAddedToExport = false;

            if (formHasAnyData(formState)) {
                let isCurrentFormValidForExport = true; 
                const currentStepConfig = stepsData[currentStep];

                if (currentStepConfig.customRenderFunctionName === 'renderRelatedProcessesStepControls' && currentStep === STEP_RELATED_PROCESSES) {
                    if (formState.hasRelatedProcesses === 'yes' && (!Array.isArray(formState.relatedProcessesArray) || !formState.relatedProcessesArray.some(p => p.trim() !== ''))) {
                        isCurrentFormValidForExport = false; 
                    } else if (formState.hasRelatedProcesses === null) {
                         isCurrentFormValidForExport = false; 
                    }
                } else if (currentStepConfig.fields && currentStepConfig.fields.length > 0) { 
                    for (const f of currentStepConfig.fields) { 
                        const container = document.getElementById(`container-${f.id}`);
                        if (container && container.classList.contains('hidden')) continue; 
                        const valueToValidate = formState[f.id] || (f.type === 'checkboxGroup' ? [] : '');
                        if (!validateSingleField(f.id, valueToValidate).isValid) {
                            isCurrentFormValidForExport = false; 
                            console.log(`Export validation: Field ${f.id} is invalid.`);
                            break;
                        }
                    }
                }
                console.log('Export: isCurrentFormValidForExport based on current step data:', isCurrentFormValidForExport);

                if (isCurrentFormValidForExport) {
                    let isAlreadySubmitted = submissions.some(sub => JSON.stringify(sub) === JSON.stringify(formState));
                    if (!isAlreadySubmitted) {
                         currentFormCanBeAddedToExport = true;
                         console.log('Current form data is valid and not a duplicate, will be added to export.');
                    } else {
                        console.log('Current form data is a duplicate of an already submitted process.');
                    }
                }
            }
            
            if (currentFormCanBeAddedToExport) {
                recordsToExport.push({ ...formState });
            }

            if (recordsToExport.length === 0) {
                showToast("Нет данных для экспорта.", "warning");
                console.log('No records to export.');
                return;
            }
            console.log('Total records for export:', recordsToExport.length);

            const allFieldsFromStepsConfig = stepsData.flatMap(step => {
                if (step.customRenderFunctionName === 'renderRelatedProcessesStepControls') {
                    return [{ id: 'relatedProcessesList_forExport', label: 'Связанные процессы (список)' }];
                }
                return step.fields || [];
            }).filter(f => f && f.id); 
            
            const uniqueFieldsConfig = [];
            const seenIds = new Set();
            for (const field of allFieldsFromStepsConfig) {
                if (!seenIds.has(field.id)) {
                    uniqueFieldsConfig.push(field);
                    seenIds.add(field.id);
                }
            }

            const headers = uniqueFieldsConfig.map(field => field.label);
            const fieldIds = uniqueFieldsConfig.map(field => field.id);

            const dataRows = recordsToExport.map(record => {
                return fieldIds.map(fieldId => {
                    let value;
                    if (fieldId === 'relatedProcessesList_forExport') {
                        value = Array.isArray(record.relatedProcessesArray) ? record.relatedProcessesArray.filter(p => p && p.trim() !== '').join('; ') : '';
                    } else {
                        value = record[fieldId];
                    }
                    if (Array.isArray(value) && fieldId !== 'relatedProcessesList_forExport') return value.join(', '); 
                    return (value !== undefined && value !== null) ? String(value) : '';
                });
            });

            const aoa = [headers, ...dataRows];
            try {
                const ws = XLSX.utils.aoa_to_sheet(aoa);
                if (aoa.length > 1 && headers.length > 0) { 
                    const colWidths = headers.map((h, i) => ({
                        wch: Math.max(
                            (h ? String(h).length : 0), 
                            ...dataRows.map(row => (row[i] ? String(row[i]).length : 0))
                        ) + 3 
                    }));
                    colWidths.forEach(col => { if (col.wch > 70) col.wch = 70; }); 
                    ws['!cols'] = colWidths;
                }
                const wb = XLSX.utils.book_new();
                XLSX.utils.book_append_sheet(wb, ws, "Данные Процессов");
                const today = new Date().toISOString().slice(0, 10);
                const fileName = `Реестр процессов_${today}.xlsx`;
                const wbout = XLSX.write(wb, { bookType: "xlsx", type: "array" });
                saveAs(new Blob([wbout], { type: "application/octet-stream" }), fileName);
                emailBlock.classList.remove('hidden');
                showToast("Данные успешно экспортированы!", 'success');
            } catch (error) {
                showToast("Произошла ошибка при экспорте. " + error.message, "error");
                console.error('Error during Excel export:', error);
            }
        }

        function copyEmail() {
            const emailText = document.getElementById('email-text').textContent;
            navigator.clipboard.writeText(emailText)
                .then(() => showToast('Email скопирован!', 'success'))
                .catch(err => {
                    showToast('Не удалось скопировать Email. Пожалуйста, скопируйте вручную.', 'warning');
                    console.error('Failed to copy email:', err);
                });
        }
        function updateCounter() { counterDisplay.textContent = `Добавлено процессов: ${submissions.length}`; }
        function showToast(msg, type = 'info') {
            const t = document.createElement('div');
            t.textContent = msg;
            t.setAttribute('role', 'alert');
            t.setAttribute('aria-live', 'assertive'); 
            let typeClasses = 'bg-gray-700 dark:bg-gray-600 text-white';
            if (type === 'success') typeClasses = 'bg-green-600 dark:bg-green-700 text-white';
            else if (type === 'warning') typeClasses = 'bg-yellow-500 dark:bg-yellow-600 text-black dark:text-gray-900';
            else if (type === 'error') typeClasses = 'bg-red-600 dark:bg-red-700 text-white';
            t.className = `${typeClasses} px-4 py-3 rounded-xl2 shadow-lg opacity-0 transition-all duration-300 ease-out transform translate-y-2`;
            toastContainer.prepend(t);
            requestAnimationFrame(() => { requestAnimationFrame(() => { t.style.opacity = '1'; t.style.transform = 'translateY(0)'; }); });
            setTimeout(() => { t.style.opacity = '0'; t.style.transform = 'translateY(10px)'; setTimeout(() => t.remove(), 350); }, type === 'warning' || type === 'error' ? 7000 : 5000);
        }
    </script>
</body>
</html>
