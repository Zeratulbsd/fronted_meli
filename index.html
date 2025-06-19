<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MercadoLibre API - Análisis de Frecuencia de Términos</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            backdrop-filter: blur(10px);
        }

        .header {
            background: linear-gradient(45deg, #FFE600, #FF6B35);
            padding: 30px;
            text-align: center;
            color: #333;
        }

        .header h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        .header p {
            font-size: 1.1rem;
            opacity: 0.8;
        }

        .main-content {
            padding: 40px;
        }

        .api-status {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 30px;
            padding: 15px;
            border-radius: 10px;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .api-status.loading {
            background: #ffeaa7;
            color: #2d3436;
        }

        .api-status.healthy {
            background: #00b894;
            color: white;
        }

        .api-status.error {
            background: #e17055;
            color: white;
        }

        .status-indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            margin-right: 10px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.5; }
            100% { opacity: 1; }
        }

        .search-section {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
        }

        .search-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: #2d3436;
            display: flex;
            align-items: center;
        }

        .search-title::before {
            content: "🔍";
            margin-right: 10px;
        }

        .search-form {
            display: grid;
            grid-template-columns: 1fr 1fr auto;
            gap: 15px;
            align-items: end;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group label {
            margin-bottom: 8px;
            font-weight: 600;
            color: #555;
        }

        .form-group input, .form-group select {
            padding: 12px 15px;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
        }

        .btn {
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .btn-primary {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(102, 126, 234, 0.3);
        }

        .btn-secondary {
            background: #6c757d;
            color: white;
        }

        .btn-secondary:hover {
            background: #5a6268;
        }

        .results-section {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            min-height: 200px;
        }

        .results-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: #2d3436;
            display: flex;
            align-items: center;
        }

        .results-title::before {
            content: "📊";
            margin-right: 10px;
        }

        .result-card {
            background: linear-gradient(135deg, #74b9ff, #0984e3);
            color: white;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 15px;
            animation: slideIn 0.5s ease;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .frequency-display {
            font-size: 2rem;
            font-weight: bold;
            text-align: center;
            margin: 10px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .stat-card {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            border-left: 4px solid #667eea;
        }

        .stat-number {
            font-size: 1.8rem;
            font-weight: bold;
            color: #667eea;
        }

        .stat-label {
            color: #6c757d;
            margin-top: 5px;
        }

        .documents-list {
            max-height: 300px;
            overflow-y: auto;
            background: #f8f9fa;
            border-radius: 8px;
            padding: 15px;
            margin-top: 15px;
        }

        .document-item {
            padding: 8px 12px;
            margin: 5px 0;
            background: white;
            border-radius: 5px;
            border-left: 3px solid #28a745;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .document-item:hover {
            background: #e8f5e8;
            transform: translateX(5px);
        }

        .loading {
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 40px;
        }

        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid #f3f3f3;
            border-top: 4px solid #667eea;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .error-message {
            background: #ffe6e6;
            color: #d63031;
            padding: 15px;
            border-radius: 8px;
            border-left: 4px solid #d63031;
            margin: 15px 0;
        }

        @media (max-width: 768px) {
            .search-form {
                grid-template-columns: 1fr;
            }
            
            .header h1 {
                font-size: 2rem;
            }
            
            .main-content {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>📚 Análisis de Frecuencia de Términos</h1>
            <p>Challenge MercadoLibre - API de Procesamiento de Documentos</p>
        </div>

        <div class="main-content">
            <div class="api-status loading" id="apiStatus">
                <div class="status-indicator"></div>
                <span id="statusText">Conectando con la API...</span>
            </div>

            <div class="search-section">
                <h2 class="search-title">Buscar Término</h2>
                <form class="search-form" id="searchForm">
                    <div class="form-group">
                        <label for="termInput">Término a buscar</label>
                        <input type="text" id="termInput" placeholder="Ej: casa, auto, mercado..." required>
                    </div>
                    <div class="form-group">
                        <label for="docSelect">Documento (opcional)</label>
                        <select id="docSelect">
                            <option value="">Búsqueda global</option>
                        </select>
                    </div>
                    <button type="submit" class="btn btn-primary">Buscar</button>
                </form>
            </div>

            <div class="results-section">
                <h2 class="results-title">Resultados</h2>
                <div id="resultsContainer">
                    <p style="text-align: center; color: #6c757d; padding: 40px;">
                        💡 Ingresa un término para comenzar la búsqueda
                    </p>
                </div>
            </div>
        </div>
    </div>

    <script>
        class MercadoLibreAPI {
            constructor() {
                this.baseUrl = this.detectBaseUrl();
                this.documents = [];
                this.init();
            }

            detectBaseUrl() {
                // Si estamos en desarrollo local
                if (window.location.hostname === 'localhost' || window.location.hostname === '127.0.0.1') {
                    return `${window.location.protocol}//${window.location.hostname}:5000`;
                }
                
                // Si estamos en producción (Heroku), usar la misma URL del sitio
                return window.location.origin;
            }

            async init() {
                await this.checkHealth();
                await this.loadDocuments();
                this.setupEventListeners();
            }

            async checkHealth() {
                const statusEl = document.getElementById('apiStatus');
                const statusText = document.getElementById('statusText');

                try {
                    const response = await fetch(`${this.baseUrl}/health`);
                    const data = await response.json();

                    if (response.ok) {
                        statusEl.className = 'api-status healthy';
                        statusText.textContent = `✅ API Conectada - ${data.message}`;
                    } else {
                        throw new Error('API no disponible');
                    }
                } catch (error) {
                    statusEl.className = 'api-status error';
                    statusText.textContent = `❌ Error de conexión - ${error.message}`;
                }
            }

            async loadDocuments() {
                try {
                    const response = await fetch(`${this.baseUrl}/documents`);
                    const data = await response.json();
                    
                    if (response.ok) {
                        this.documents = data.documents;
                        this.populateDocumentSelect();
                    }
                } catch (error) {
                    console.error('Error cargando documentos:', error);
                }
            }

            populateDocumentSelect() {
                const select = document.getElementById('docSelect');
                
                // Limpiar opciones existentes (excepto la primera)
                while (select.children.length > 1) {
                    select.removeChild(select.lastChild);
                }

                // Agregar documentos
                this.documents.forEach(doc => {
                    const option = document.createElement('option');
                    option.value = doc;
                    option.textContent = doc;
                    select.appendChild(option);
                });
            }

            setupEventListeners() {
                const form = document.getElementById('searchForm');
                form.addEventListener('submit', (e) => {
                    e.preventDefault();
                    this.searchTerm();
                });

                const docSelect = document.getElementById('docSelect');
                docSelect.addEventListener('change', () => {
                    const termInput = document.getElementById('termInput');
                    if (termInput.value.trim()) {
                        this.searchTerm();
                    }
                });
            }

            async searchTerm() {
                const term = document.getElementById('termInput').value.trim();
                const docName = document.getElementById('docSelect').value;
                const resultsContainer = document.getElementById('resultsContainer');

                if (!term) {
                    this.showError('Por favor ingresa un término para buscar');
                    return;
                }

                // Mostrar loading
                resultsContainer.innerHTML = `
                    <div class="loading">
                        <div class="spinner"></div>
                        <span style="margin-left: 15px;">Buscando término...</span>
                    </div>
                `;

                try {
                    let url = `${this.baseUrl}/?term=${encodeURIComponent(term)}`;
                    if (docName) {
                        url += `&doc_name=${encodeURIComponent(docName)}`;
                    }

                    const response = await fetch(url);
                    const data = await response.json();

                    if (response.ok) {
                        this.displayResults(data);
                        await this.loadStats();
                    } else {
                        this.showError(data.error || 'Error en la búsqueda');
                    }
                } catch (error) {
                    this.showError(`Error de conexión: ${error.message}`);
                }
            }

            displayResults(data) {
                const resultsContainer = document.getElementById('resultsContainer');
                
                const scope = data.document ? `en "${data.document}"` : 'en toda la colección';
                
                resultsContainer.innerHTML = `
                    <div class="result-card">
                        <h3>Término: "${data.term}"</h3>
                        <div class="frequency-display">${data.frecuencia.toLocaleString()}</div>
                        <p>apariciones ${scope}</p>
                    </div>
                `;
            }

            async loadStats() {
                try {
                    const response = await fetch(`${this.baseUrl}/stats`);
                    const stats = await response.json();

                    if (response.ok) {
                        this.displayStats(stats);
                    }
                } catch (error) {
                    console.error('Error cargando estadísticas:', error);
                }
            }

            displayStats(stats) {
                const resultsContainer = document.getElementById('resultsContainer');
                
                resultsContainer.innerHTML += `
                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-number">${stats.total_documents.toLocaleString()}</div>
                            <div class="stat-label">Documentos</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number">${stats.total_unique_terms.toLocaleString()}</div>
                            <div class="stat-label">Términos únicos</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number">${stats.total_terms.toLocaleString()}</div>
                            <div class="stat-label">Total términos</div>
                        </div>
                    </div>
                    <div class="documents-list">
                        <h4>📄 Documentos disponibles:</h4>
                        ${stats.documents.map(doc => `
                            <div class="document-item" onclick="api.selectDocument('${doc}')">${doc}</div>
                        `).join('')}
                    </div>
                `;
            }

            selectDocument(docName) {
                const docSelect = document.getElementById('docSelect');
                docSelect.value = docName;
                
                const termInput = document.getElementById('termInput');
                if (termInput.value.trim()) {
                    this.searchTerm();
                }
            }

            showError(message) {
                const resultsContainer = document.getElementById('resultsContainer');
                resultsContainer.innerHTML = `
                    <div class="error-message">
                        ❌ ${message}
                    </div>
                `;
            }
        }

        // Inicializar la aplicación
        const api = new MercadoLibreAPI();
    </script>
</body>
</html>
