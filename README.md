# my-roblox-scripts
scripts <!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Архив скриптов Roblox</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
            min-height: 100vh;
            color: #ffffff;
            overflow-x: hidden;
            position: relative;
        }

        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                radial-gradient(circle at 20% 80%, rgba(120, 119, 198, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(119, 198, 255, 0.05) 0%, transparent 50%);
            pointer-events: none;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        .header {
            text-align: center;
            padding: 50px 20px;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }

        .header h1 {
            font-size: 3.2rem;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
            font-weight: 800;
            letter-spacing: -0.5px;
        }

        .header p {
            font-size: 1.3rem;
            opacity: 0.9;
            color: #e2e8f0;
            font-weight: 300;
        }

        .auth-section {
            background: rgba(255, 255, 255, 0.08);
            padding: 35px;
            border-radius: 18px;
            text-align: center;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
        }

        .auth-input {
            padding: 16px 28px;
            font-size: 17px;
            background: rgba(255, 255, 255, 0.12);
            border: 2px solid rgba(255, 255, 255, 0.25);
            border-radius: 14px;
            width: 320px;
            margin-right: 18px;
            color: white;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .auth-input:focus {
            outline: none;
            border-color: #667eea;
            background: rgba(255, 255, 255, 0.18);
            box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.15);
        }

        .auth-input::placeholder {
            color: rgba(255, 255, 255, 0.6);
            font-weight: 400;
        }

        .auth-btn {
            padding: 16px 40px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 14px;
            font-size: 17px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            letter-spacing: 0.5px;
        }

        .auth-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(102, 126, 234, 0.4);
        }

        .main-content {
            display: none;
        }

        .editor-panel {
            background: rgba(255, 255, 255, 0.08);
            padding: 35px;
            border-radius: 20px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
        }

        .panel-title {
            font-size: 1.7rem;
            margin-bottom: 28px;
            color: #667eea;
            font-weight: 700;
            letter-spacing: -0.3px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 28px;
            margin-bottom: 28px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-label {
            margin-bottom: 10px;
            font-weight: 600;
            color: #e2e8f0;
            font-size: 15px;
        }

        .form-input {
            padding: 14px 20px;
            background: rgba(255, 255, 255, 0.12);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 12px;
            color: white;
            font-size: 16px;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .form-input:focus {
            outline: none;
            border-color: #667eea;
            background: rgba(255, 255, 255, 0.18);
            box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.15);
        }

        .code-editor {
            grid-column: 1 / -1;
            min-height: 220px;
            font-family: 'Consolas', 'Monaco', monospace;
            resize: vertical;
            line-height: 1.5;
        }

        .action-buttons {
            display: flex;
            gap: 18px;
            justify-content: flex-end;
        }

        .btn-primary {
            padding: 14px 35px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.35);
        }

        .btn-secondary {
            padding: 14px 35px;
            background: rgba(255, 255, 255, 0.12);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
        }

        .scripts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(480px, 1fr));
            gap: 28px;
        }

        .script-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 18px;
            padding: 28px;
            border: 1px solid rgba(255, 255, 255, 0.15);
            transition: all 0.3s ease;
            position: relative;
            backdrop-filter: blur(10px);
        }

        .script-card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.12);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
            border-color: rgba(102, 126, 234, 0.3);
        }

        .script-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 18px;
        }

        .script-title {
            font-size: 1.4rem;
            font-weight: 700;
            color: #667eea;
            margin-bottom: 8px;
        }

        .script-description {
            color: #cbd5e0;
            font-size: 1rem;
            line-height: 1.5;
        }

        .script-date {
            font-size: 0.85rem;
            color: rgba(255, 255, 255, 0.6);
            background: rgba(255, 255, 255, 0.12);
            padding: 6px 12px;
            border-radius: 8px;
            font-weight: 500;
        }

        .script-code {
            background: #1a202c;
            color: #e2e8f0;
            padding: 22px;
            border-radius: 12px;
            font-family: 'Consolas', 'Monaco', monospace;
            font-size: 14px;
            white-space: pre-wrap;
            word-wrap: break-word;
            max-height: 320px;
            overflow-y: auto;
            margin-bottom: 22px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            line-height: 1.6;
        }

        .script-actions {
            display: flex;
            gap: 12px;
            justify-content: flex-end;
        }

        .btn-copy {
            padding: 10px 24px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-copy:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 18px rgba(102, 126, 234, 0.35);
        }

        .btn-delete {
            padding: 10px 24px;
            background: rgba(255, 255, 255, 0.12);
            color: #fc8181;
            border: 2px solid #fc8181;
            border-radius: 10px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-delete:hover {
            background: #fc8181;
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 6px 18px rgba(252, 129, 129, 0.3);
        }

        .message {
            padding: 16px 22px;
            border-radius: 12px;
            margin: 18px 0;
            text-align: center;
            font-weight: 600;
            font-size: 15px;
            backdrop-filter: blur(10px);
        }

        .error {
            background: rgba(252, 129, 129, 0.15);
            color: #fc8181;
            border: 1px solid rgba(252, 129, 129, 0.3);
        }

        .success {
            background: rgba(72, 187, 120, 0.15);
            color: #48bb78;
            border: 1px solid rgba(72, 187, 120, 0.3);
        }

        .empty-state {
            grid-column: 1 / -1;
            text-align: center;
            padding: 70px 25px;
            color: #cbd5e0;
        }

        .empty-state h3 {
            font-size: 1.6rem;
            margin-bottom: 12px;
            color: #667eea;
            font-weight: 700;
        }

        .empty-state p {
            font-size: 1.1rem;
            opacity: 0.8;
        }

        @media (max-width: 768px) {
            .form-grid {
                grid-template-columns: 1fr;
            }
            
            .scripts-grid {
                grid-template-columns: 1fr;
            }
            
            .auth-input {
                width: 100%;
                margin-right: 0;
                margin-bottom: 18px;
            }

            .header h1 {
                font-size: 2.5rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Архив скриптов Roblox</h1>
            <p>Безопасное хранение и управление вашими скриптами</p>
        </div>

        <div class="auth-section" id="authSection">
            <input type="password" class="auth-input" id="passwordInput" placeholder="Введите пароль для доступа">
            <button class="auth-btn" onclick="checkPassword()">Получить доступ</button>
            <div id="authMessage" class="message error" style="display: none;"></div>
        </div>

        <div class="main-content" id="mainContent">
            <div class="editor-panel">
                <h2 class="panel-title">Добавить новый скрипт</h2>
                <div class="form-grid">
                    <div class="form-group">
                        <label class="form-label">Название скрипта</label>
                        <input type="text" class="form-input" id="scriptTitle" placeholder="Авто-ферма, TP скрипт и т.д.">
                    </div>
                    <div class="form-group">
                        <label class="form-label">Категория</label>
                        <input type="text" class="form-input" id="scriptCategory" placeholder="Автоматизация, Телепорт, GUI">
                    </div>
                    <div class="form-group" style="grid-column: 1 / -1;">
                        <label class="form-label">Описание скрипта</label>
                        <input type="text" class="form-input" id="scriptDescription" placeholder="Подробное описание функционала">
                    </div>
                    <div class="form-group" style="grid-column: 1 / -1;">
                        <label class="form-label">Код Lua</label>
                        <textarea class="form-input code-editor" id="scriptCode" placeholder="Вставьте ваш Lua код здесь..."></textarea>
                    </div>
                </div>
                <div class="action-buttons">
                    <button class="btn-secondary" onclick="clearForm()">Очистить форму</button>
                    <button class="btn-primary" onclick="addScript()">Опубликовать скрипт</button>
                </div>
                <div id="formMessage" class="message" style="display: none;"></div>
            </div>

            <div class="editor-panel">
                <h2 class="panel-title">Опубликованные скрипты</h2>
                <div class="scripts-grid" id="scriptsGrid">
                    <div class="empty-state">
                        <h3>Пока нет опубликованных скриптов</h3>
                        <p>Добавьте ваш первый скрипт используя форму выше</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        const SITE_PASSWORD = "YU%RU@Pue0!2d$a21a";
        
        function checkPassword() {
            const input = document.getElementById('passwordInput').value;
            const message = document.getElementById('authMessage');
            const mainContent = document.getElementById('mainContent');
            const authSection = document.getElementById('authSection');
            
            if (input === SITE_PASSWORD) {
                mainContent.style.display = 'block';
                authSection.style.display = 'none';
                loadScripts();
            } else {
                message.textContent = 'Неверный пароль доступа';
                message.style.display = 'block';
                setTimeout(() => {
                    message.style.display = 'none';
                }, 3000);
            }
        }
        
        function loadScripts() {
            const scriptsGrid = document.getElementById('scriptsGrid');
            const scripts = JSON.parse(localStorage.getItem('robloxScripts') || '[]');
            
            scriptsGrid.innerHTML = '';
            
            if (scripts.length === 0) {
                scriptsGrid.innerHTML = `
                    <div class="empty-state">
                        <h3>Пока нет опубликованных скриптов</h3>
                        <p>Добавьте ваш первый скрипт используя форму выше</p>
                    </div>
                `;
                return;
            }
            
            scripts.forEach((script, index) => {
                const scriptCard = document.createElement('div');
                scriptCard.className = 'script-card';
                scriptCard.innerHTML = `
                    <div class="script-header">
                        <div>
                            <div class="script-title">${escapeHtml(script.title)}</div>
                            <div class="script-description">${escapeHtml(script.description)}</div>
                        </div>
                        <div class="script-date">${script.date || 'Сегодня'}</div>
                    </div>
                    <div class="script-code">${escapeHtml(script.code)}</div>
                    <div class="script-actions">
                        <button class="btn-copy" onclick="copyToClipboard(${index})">Копировать код</button>
                        <button class="btn-delete" onclick="deleteScript(${index})">Удалить пост</button>
                    </div>
                `;
                scriptsGrid.appendChild(scriptCard);
            });
        }
        
        function addScript() {
            const title = document.getElementById('scriptTitle').value.trim();
            const category = document.getElementById('scriptCategory').value.trim();
            const description = document.getElementById('scriptDescription').value.trim();
            const code = document.getElementById('scriptCode').value.trim();
            const message = document.getElementById('formMessage');
            
            if (!title || !code) {
                showMessage('Заполните название и код скрипта', 'error');
                return;
            }
            
            const scripts = JSON.parse(localStorage.getItem('robloxScripts') || '[]');
            const newScript = {
                title: title,
                category: category,
                description: description,
                code: code,
                date: new Date().toLocaleDateString('ru-RU')
            };
            
            scripts.unshift(newScript);
            localStorage.setItem('robloxScripts', JSON.stringify(scripts));
            
            clearForm();
            showMessage('Скрипт успешно опубликован', 'success');
            loadScripts();
        }
        
        function deleteScript(index) {
            if (confirm('Вы уверены что хотите удалить этот скрипт?')) {
                const scripts = JSON.parse(localStorage.getItem('robloxScripts') || '[]');
                scripts.splice(index, 1);
                localStorage.setItem('robloxScripts', JSON.stringify(scripts));
                loadScripts();
                showMessage('Скрипт удален', 'success');
            }
        }
        
        function copyToClipboard(index) {
            const scripts = JSON.parse(localStorage.getItem('robloxScripts') || '[]');
            const script = scripts[index];
            
            navigator.clipboard.writeText(script.code).then(() => {
                showMessage('Код скопирован в буфер обмена', 'success');
            }).catch(() => {
                showMessage('Ошибка копирования', 'error');
            });
        }
        
        function clearForm() {
            document.getElementById('scriptTitle').value = '';
            document.getElementById('scriptCategory').value = '';
            document.getElementById('scriptDescription').value = '';
            document.getElementById('scriptCode').value = '';
        }
        
        function showMessage(text, type) {
            const message = document.getElementById('formMessage');
            message.textContent = text;
            message.className = `message ${type}`;
            message.style.display = 'block';
            
            setTimeout(() => {
                message.style.display = 'none';
            }, 3000);
        }
        
        function escapeHtml(text) {
            const div = document.createElement('div');
            div.textContent = text;
            return div.innerHTML;
        }
        
        document.getElementById('passwordInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                checkPassword();
            }
        });
        
        document.getElementById('scriptCode').addEventListener('keydown', function(e) {
            if (e.key === 'Tab') {
                e.preventDefault();
                const start = this.selectionStart;
                const end = this.selectionEnd;
                
                this.value = this.value.substring(0, start) + '    ' + this.value.substring(end);
                this.selectionStart = this.selectionEnd = start + 4;
            }
        });
    </script>
</body>
</html>

