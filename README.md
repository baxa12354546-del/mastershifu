<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🌍 Естественные науки: Путешествие в природу</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #2c3e50 0%, #4ca1af 100%);
            color: white;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        /* Заголовок */
        .game-header {
            text-align: center;
            margin-bottom: 40px;
            padding: 30px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 25px;
            border: 4px solid #3498db;
        }
        
        .game-title {
            font-size: 3em;
            margin-bottom: 15px;
            color: #fff;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
        }
        
        .game-subtitle {
            font-size: 1.3em;
            opacity: 0.9;
            color: #ecf0f1;
        }
        
        /* Основная игровая область */
        .game-area {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
            margin-bottom: 30px;
        }
        
        /* Лаборатория/природная сцена */
        .science-lab {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            border: 5px solid #2ecc71;
            color: #2c3e50;
        }
        
        .scene-container {
            position: relative;
            min-height: 400px;
            border-radius: 20px;
            overflow: hidden;
            background: linear-gradient(to bottom, #87CEEB, #98FB98);
            margin-bottom: 25px;
        }
        
        /* Природные элементы */
        .sun {
            position: absolute;
            top: 30px;
            right: 30px;
            width: 80px;
            height: 80px;
            background: radial-gradient(circle at 30% 30%, #FFD700, #FF8C00);
            border-radius: 50%;
            box-shadow: 0 0 30px #FFD700;
        }
        
        .tree {
            position: absolute;
            bottom: 0;
            left: 50px;
            width: 60px;
            height: 150px;
            background: #8B4513;
        }
        
        .tree::after {
            content: "";
            position: absolute;
            bottom: 140px;
            left: -70px;
            width: 200px;
            height: 120px;
            background: #228B22;
            border-radius: 100px 100px 0 0;
        }
        
        .river {
            position: absolute;
            bottom: 0;
            left: 200px;
            width: 100px;
            height: 50px;
            background: #1E90FF;
            border-radius: 50px 50px 0 0;
        }
        
        /* Интерактивные объекты */
        .interactive-object {
            position: absolute;
            cursor: pointer;
            transition: all 0.3s ease;
            z-index: 10;
        }
        
        .interactive-object:hover {
            transform: scale(1.2);
            filter: drop-shadow(0 0 10px rgba(255, 255, 0, 0.7));
        }
        
        .plant {
            width: 60px;
            height: 60px;
            background: #32CD32;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2em;
            border: 3px solid #228B22;
        }
        
        .animal {
            width: 70px;
            height: 70px;
            background: #DEB887;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5em;
            border: 3px solid #A0522D;
        }
        
        .water {
            width: 60px;
            height: 60px;
            background: #00BFFF;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2em;
            border: 3px solid #1E90FF;
        }
        
        /* Панель управления */
        .control-panel {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            border: 5px solid #9B59B6;
            color: #2c3e50;
        }
        
        /* Категории обучения */
        .category-selector {
            margin-bottom: 30px;
        }
        
        .category-title {
            font-size: 1.5em;
            color: #2c3e50;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .category-buttons {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .category-btn {
            padding: 15px;
            background: #ecf0f1;
            border: 3px solid #3498db;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
            color: #2c3e50;
            text-align: center;
        }
        
        .category-btn:hover {
            background: #3498db;
            color: white;
            transform: translateY(-5px);
        }
        
        .category-btn.active {
            background: #2980b9;
            color: white;
            border-color: #2980b9;
        }
        
        /* Вопросы и ответы */
        .question-box {
            background: #e8f4f8;
            border-radius: 20px;
            padding: 25px;
            margin-bottom: 25px;
            border: 3px solid #3498db;
        }
        
        .question-text {
            font-size: 1.4em;
            margin-bottom: 20px;
            color: #2c3e50;
            line-height: 1.5;
        }
        
        .options-grid {
            display: grid;
            gap: 15px;
        }
        
        .option-btn {
            padding: 15px;
            background: white;
            border: 2px solid #bdc3c7;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: left;
            font-size: 1.1em;
            color: #2c3e50;
        }
        
        .option-btn:hover {
            background: #f1f2f6;
            border-color: #3498db;
        }
        
        .option-btn.selected {
            background: #3498db;
            color: white;
            border-color: #2980b9;
        }
        
        /* Кнопки действий */
        .action-buttons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .action-btn {
            flex: 1;
            padding: 15px;
            border: none;
            border-radius: 15px;
            cursor: pointer;
            font-weight: bold;
            font-size: 1.1em;
            transition: all 0.3s ease;
        }
        
        .submit-btn {
            background: #2ecc71;
            color: white;
        }
        
        .submit-btn:hover:not(:disabled) {
            background: #27ae60;
            transform: translateY(-3px);
        }
        
        .submit-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }
        
        .next-btn {
            background: #3498db;
            color: white;
        }
        
        .next-btn:hover {
            background: #2980b9;
            transform: translateY(-3px);
        }
        
        /* Панель знаний */
        .knowledge-panel {
            background: #fff9e6;
            border-radius: 20px;
            padding: 25px;
            margin-top: 25px;
            border: 3px solid #f1c40f;
            display: none;
        }
        
        .knowledge-title {
            font-size: 1.4em;
            color: #d35400;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .knowledge-content {
            font-size: 1.1em;
            line-height: 1.6;
            color: #2c3e50;
        }
        
        /* Прогресс */
        .progress-panel {
            background: #e8f6f3;
            border-radius: 20px;
            padding: 20px;
            margin-top: 25px;
            border: 3px solid #1abc9c;
        }
        
        .progress-title {
            font-size: 1.3em;
            color: #16a085;
            margin-bottom: 15px;
        }
        
        .progress-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            text-align: center;
        }
        
        .progress-item {
            background: white;
            border-radius: 15px;
            padding: 15px;
            border: 2px solid #1abc9c;
        }
        
        .progress-value {
            font-size: 2em;
            font-weight: bold;
            color: #1abc9c;
        }
        
        .progress-label {
            font-size: 0.9em;
            color: #7f8c8d;
            margin-top: 5px;
        }
        
        /* ================= Новые элементы: уровни и монеты ================= */
        
        /* Панель уровней */
        .levels-panel {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            border: 5px solid #e74c3c;
            color: #2c3e50;
            margin-bottom: 30px;
            display: none;
        }
        
        .levels-title {
            font-size: 1.8em;
            color: #2c3e50;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .levels-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 15px;
            margin-bottom: 30px;
        }
        
        .level-card {
            background: #ecf0f1;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 3px solid #bdc3c7;
            position: relative;
        }
        
        .level-card:hover:not(.locked) {
            background: #3498db;
            color: white;
            transform: translateY(-5px);
        }
        
        .level-card.active {
            background: #2ecc71;
            color: white;
            border-color: #27ae60;
        }
        
        .level-card.locked {
            background: #95a5a6;
            color: #bdc3c7;
            cursor: not-allowed;
        }
        
        .level-number {
            font-size: 2.2em;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .level-reward {
            font-size: 1.1em;
            margin-top: 10px;
            color: #f39c12;
            font-weight: bold;
        }
        
        /* Магазин */
        .shop-panel {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            border: 5px solid #f39c12;
            color: #2c3e50;
            margin-bottom: 30px;
            display: none;
        }
        
        .shop-title {
            font-size: 1.8em;
            color: #2c3e50;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .shop-items {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .shop-item {
            background: white;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            border: 3px solid #ddd;
            transition: all 0.3s ease;
        }
        
        .shop-item:hover {
            border-color: #3498db;
            transform: translateY(-5px);
        }
        
        .shop-item-icon {
            font-size: 3em;
            margin-bottom: 15px;
            display: block;
        }
        
        .shop-item-price {
            font-size: 1.3em;
            color: #27ae60;
            font-weight: bold;
            margin: 15px 0;
        }
        
        .buy-btn {
            padding: 10px 20px;
            background: #2ecc71;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
            width: 100%;
        }
        
        .buy-btn:hover:not(:disabled) {
            background: #27ae60;
            transform: scale(1.05);
        }
        
        .buy-btn:disabled {
            background: #bdc3c7;
            cursor: not-allowed;
        }
        
        /* Инвентарь */
        .inventory-panel {
            background: #e8f6f3;
            border-radius: 20px;
            padding: 20px;
            border: 3px solid #1abc9c;
        }
        
        .inventory-title {
            font-size: 1.3em;
            color: #16a085;
            margin-bottom: 15px;
        }
        
        .inventory-items {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .inventory-item {
            background: white;
            border-radius: 10px;
            padding: 10px 15px;
            border: 2px solid #ddd;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        /* Отображение монет */
        .coins-display {
            position: absolute;
            top: 20px;
            right: 20px;
            background: linear-gradient(135deg, #FFD700, #FFA500);
            padding: 10px 20px;
            border-radius: 50px;
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: bold;
            font-size: 1.2em;
            color: #8B4513;
            border: 3px solid #DAA520;
            box-shadow: 0 4px 15px rgba(255, 215, 0, 0.4);
        }
        
        /* ================= Оригинальная система сада ================= */
        .garden-panel {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            border: 5px solid #2ecc71;
            color: #2c3e50;
            margin-bottom: 30px;
            display: none;
        }
        
        .flower-container {
            position: relative;
            height: 300px;
            margin: 20px 0;
            background: linear-gradient(to bottom, #87CEEB, #98FB98);
            border-radius: 20px;
            overflow: hidden;
        }
        
        .flower-pot {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 80px;
            background: #8B4513;
            border-radius: 10px 10px 0 0;
        }
        
        .flower-stem {
            position: absolute;
            bottom: 80px;
            left: 50%;
            transform: translateX(-50%);
            width: 10px;
            height: 0;
            background: #32CD32;
            transition: height 2s ease;
        }
        
        .flower-head {
            position: absolute;
            width: 0;
            height: 0;
            background: #FF69B4;
            border-radius: 50%;
            transition: all 2s ease;
            opacity: 0;
        }
        
        /* Радужный эффект */
        .rainbow-flower {
            background: linear-gradient(45deg, 
                #FF0000, #FF7F00, #FFFF00, #00FF00, 
                #0000FF, #4B0082, #8B00FF) !important;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
        }
        
        /* Анимации */
        @keyframes correct {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        @keyframes incorrect {
            0% { transform: translateX(0); }
            25% { transform: translateX(-10px); }
            75% { transform: translateX(10px); }
            100% { transform: translateX(0); }
        }
        
        .correct-animation {
            animation: correct 0.5s ease;
            background: #2ecc71 !important;
            color: white !important;
        }
        
        .incorrect-animation {
            animation: incorrect 0.5s ease;
            background: #e74c3c !important;
            color: white !important;
        }
        
        /* Адаптивный дизайн */
        @media (max-width: 768px) {
            .game-area {
                grid-template-columns: 1fr;
            }
            
            .game-title {
                font-size: 2.2em;
            }
            
            .category-buttons {
                grid-template-columns: 1fr;
            }
            
            .progress-grid {
                grid-template-columns: 1fr;
            }
            
            .levels-grid {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .shop-items {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Отображение монет -->
    <div class="coins-display">
        <span>🪙</span>
        <span id="coinsCount">100</span>
    </div>
    
    <div class="container">
        <!-- Заголовок -->
        <div class="game-header">
            <h1 class="game-title">🌍 Естественные науки: Путешествие в природу</h1>
            <p class="game-subtitle">Изучайте природные знания через игры и исследования!</p>
        </div>
        
        <!-- Навигационные кнопки -->
        <div class="category-buttons" style="margin-bottom: 30px;">
            <button class="category-btn" onclick="showGame()">
                🎮 Игра
            </button>
            <button class="category-btn" onclick="showLevels()">
                🏆 Уровни
            </button>
            <button class="category-btn" onclick="showShop()">
                🏪 Магазин
            </button>
            <button class="category-btn" onclick="showGarden()">
                🌷 Мой сад
            </button>
        </div>
        
        <!-- Основная игровая область -->
        <div id="gameSection" class="game-area">
            <!-- Природная лаборатория -->
            <div class="science-lab">
                <div class="scene-container">
                    <!-- Природные элементы -->
                    <div class="sun"></div>
                    <div class="tree"></div>
                    <div class="river"></div>
                    
                    <!-- Интерактивные объекты -->
                    <div class="interactive-object plant" style="left: 150px; bottom: 100px;" onclick="showPlantInfo()">
                        🌻
                    </div>
                    <div class="interactive-object animal" style="left: 250px; bottom: 50px;" onclick="showAnimalInfo()">
                        🐇
                    </div>
                    <div class="interactive-object water" style="left: 350px; bottom: 80px;" onclick="showWaterInfo()">
                        💧
                    </div>
                    <div class="interactive-object plant" style="left: 450px; bottom: 120px;" onclick="showTreeInfo()">
                        🌳
                    </div>
                </div>
                
                <!-- Информация о природе -->
                <div class="nature-info">
                    <h3 style="color: #2c3e50; margin-bottom: 15px;">🔍 Нажмите на объекты в природе, чтобы узнать больше!</h3>
                    <p id="natureDescription" style="color: #34495e; line-height: 1.6;">
                        Добро пожаловать в мир естественных наук! Здесь вы можете изучать растения, животных, воду и воздух.
                        Нажимайте на объекты в природной сцене, чтобы узнать интересные факты.
                    </p>
                </div>
            </div>
            
            <!-- Панель управления -->
            <div class="control-panel">
                <!-- Выбор категории -->
                <div class="category-selector">
                    <h2 class="category-title">📚 Выберите тему обучения</h2>
                    <div class="category-buttons">
                        <button class="category-btn active" onclick="selectCategory('plants')">
                            🌱 Растения
                        </button>
                        <button class="category-btn" onclick="selectCategory('animals')">
                            🐾 Животные
                        </button>
                        <button class="category-btn" onclick="selectCategory('water')">
                            💧 Вода
                        </button>
                        <button class="category-btn" onclick="selectCategory('weather')">
                            ☀️ Погода
                        </button>
                    </div>
                </div>
                
                <!-- Вопрос -->
                <div class="question-box">
                    <div class="question-text" id="questionText">
                        Какой частью растения впитывается вода?
                    </div>
                    <div class="options-grid" id="optionsGrid">
                        <!-- Опции загружаются через JS -->
                    </div>
                </div>
                
                <!-- Кнопки действий -->
                <div class="action-buttons">
                    <button class="action-btn submit-btn" id="submitBtn" onclick="checkAnswer()" disabled>
                        ✅ Проверить ответ
                    </button>
                    <button class="action-btn next-btn" id="nextBtn" onclick="nextQuestion()" style="display: none;">
                        ➡️ Следующий вопрос
                    </button>
                </div>
                
                <!-- Панель знаний -->
                <div class="knowledge-panel" id="knowledgePanel">
                    <h3 class="knowledge-title" id="knowledgeTitle">📖 Новое знание</h3>
                    <div class="knowledge-content" id="knowledgeContent">
                        Здесь будет интересная информация о природе!
                    </div>
                </div>
                
                <!-- Прогресс -->
                <div class="progress-panel">
                    <h3 class="progress-title">🏆 Ваш прогресс</h3>
                    <div class="progress-grid">
                        <div class="progress-item">
                            <div class="progress-value" id="score">0</div>
                            <div class="progress-label">Очки</div>
                        </div>
                        <div class="progress-item">
                            <div class="progress-value" id="correctAnswers">0</div>
                            <div class="progress-label">Правильно</div>
                        </div>
                        <div class="progress-item">
                            <div class="progress-value" id="questionsAnswered">0</div>
                            <div class="progress-label">Отвечено</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Панель уровней -->
        <div id="levelsSection" class="levels-panel">
            <h2 class="levels-title">🏆 Игровые уровни</h2>
            <p style="color: #34495e; margin-bottom: 20px; line-height: 1.6;">
                От новичка до мастера природы - пройдите все уровни! Каждый уровень дает больше наград.
            </p>
            
            <div class="levels-grid" id="levelsGrid">
                <!-- Уровни загружаются через JS -->
            </div>
            
            <div style="background: #e8f4f8; border-radius: 15px; padding: 20px; margin-top: 20px;">
                <h3 style="color: #2c3e50; margin-bottom: 15px;">📊 Ваш прогресс по уровням</h3>
                <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; text-align: center;">
                    <div>
                        <div style="font-size: 2em; font-weight: bold; color: #3498db;" id="completedLevels">0</div>
                        <div style="color: #7f8c8d;">Пройдено уровней</div>
                    </div>
                    <div>
                        <div style="font-size: 2em; font-weight: bold; color: #2ecc71;" id="totalCoinsEarned">0</div>
                        <div style="color: #7f8c8d;">Всего монет</div>
                    </div>
                    <div>
                        <div style="font-size: 2em; font-weight: bold; color: #9b59b6;" id="totalStars">0</div>
                        <div style="color: #7f8c8d;">Всего звезд</div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Магазин -->
        <div id="shopSection" class="shop-panel">
            <h2 class="shop-title">🏪 Магазин</h2>
            <p style="color: #34495e; margin-bottom: 20px; line-height: 1.6;">
                Покупайте полезные предметы для сада на заработанные монеты!
            </p>
            
            <div class="shop-items" id="shopItems">
                <!-- Товары загружаются через JS -->
            </div>
            
            <!-- Инвентарь -->
            <div class="inventory-panel">
                <h3 class="inventory-title">🎒 Ваш инвентарь</h3>
                <div class="inventory-items" id="inventoryItems">
                    <!-- Инвентарь загружается через JS -->
                </div>
            </div>
        </div>
        
        <!-- Оригинальный сад -->
        <div id="gardenSection" class="garden-panel">
            <h2 class="levels-title">🌷 Мой сад</h2>
            <p style="color: #34495e; margin-bottom: 20px; line-height: 1.6;">
                Выращивайте свой волшебный цветок! Поливайте и удобряйте его, чтобы он рос здоровым.
            </p>
            
            <div class="flower-container">
                <div class="flower-pot"></div>
                <div id="flowerStem" class="flower-stem"></div>
                <div id="flowerHead" class="flower-head"></div>
            </div>
            
            <div style="background: #e8f4f8; border-radius: 15px; padding: 20px; margin-top: 20px;">
                <h3 style="color: #2c3e50; margin-bottom: 15px;">📊 Состояние цветка</h3>
                
                <div style="margin-bottom: 15px;">
                    <div style="display: flex; justify-content: space-between; margin-bottom: 5px;">
                        <span style="color: #3498db;">💧 Влажность:</span>
                        <span id="waterStat">50%</span>
                    </div>
                    <div style="height: 15px; background: #ecf0f1; border-radius: 7px; overflow: hidden;">
                        <div id="waterFill" style="height: 100%; background: #3498db; width: 50%; border-radius: 7px;"></div>
                    </div>
                </div>
                
                <div style="margin-bottom: 15px;">
                    <div style="display: flex; justify-content: space-between; margin-bottom: 5px;">
                        <span style="color: #2ecc71;">🌿 Удобрение:</span>
                        <span id="fertilizerStat">50%</span>
                    </div>
                    <div style="height: 15px; background: #ecf0f1; border-radius: 7px; overflow: hidden;">
                        <div id="fertilizerFill" style="height: 100%; background: #2ecc71; width: 50%; border-radius: 7px;"></div>
                    </div>
                </div>
                
                <div>
                    <div style="display: flex; justify-content: space-between; margin-bottom: 5px;">
                        <span style="color: #e74c3c;">❤️ Здоровье:</span>
                        <span id="healthStat">100%</span>
                    </div>
                    <div style="height: 15px; background: #ecf0f1; border-radius: 7px; overflow: hidden;">
                        <div id="healthFill" style="height: 100%; background: #e74c3c; width: 100%; border-radius: 7px;"></div>
                    </div>
                </div>
                
                <div style="margin-top: 20px; display: flex; gap: 15px;">
                    <button class="action-btn" onclick="waterFlower()" style="background: #3498db;">
                        💧 Полить
                    </button>
                    <button class="action-btn" onclick="fertilizeFlower()" style="background: #2ecc71;">
                        🌿 Удобрить
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // ===================== Полные игровые данные =====================
        const gameData = {
            currentCategory: 'plants',
            currentLevel: 1,
            totalLevels: 10,
            isLevelMode: false, // Разделение обычного режима и режима уровней
            
            // Система монет
            coins: 100,
            
            // Система цветов (оригинальная)
            flower: {
                water: 50,
                fertilizer: 50,
                health: 100,
                growth: 0,
                level: 1,
                isRainbow: false
            },
            
            // Система уровней (оригинальная - завершение уровня разблокирует следующий)
            levels: {
                1: { 
                    unlocked: true, 
                    completed: false, 
                    stars: 0, 
                    reward: 50,
                    name: "Введение в природу",
                    difficulty: "Легкий",
                    questions: 5,
                    categories: ['plants']
                },
                2: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 60,
                    name: "Мир животных",
                    difficulty: "Легкий",
                    questions: 5,
                    categories: ['animals']
                },
                3: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 70,
                    name: "Тайны воды",
                    difficulty: "Легкий",
                    questions: 5,
                    categories: ['water']
                },
                4: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 80,
                    name: "Погодные явления",
                    difficulty: "Легкий",
                    questions: 5,
                    categories: ['weather']
                },
                5: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 100,
                    name: "Растения и животные",
                    difficulty: "Средний",
                    questions: 8,
                    categories: ['plants', 'animals']
                },
                6: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 120,
                    name: "Вода и погода",
                    difficulty: "Средний",
                    questions: 8,
                    categories: ['water', 'weather']
                },
                7: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 150,
                    name: "Экологический баланс",
                    difficulty: "Трудный",
                    questions: 10,
                    categories: ['plants', 'animals', 'water']
                },
                8: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 180,
                    name: "Природные циклы",
                    difficulty: "Трудный",
                    questions: 10,
                    categories: ['plants', 'water', 'weather']
                },
                9: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 220,
                    name: "Мастер природы",
                    difficulty: "Эксперт",
                    questions: 12,
                    categories: ['animals', 'water', 'weather']
                },
                10: { 
                    unlocked: false, 
                    completed: false, 
                    stars: 0, 
                    reward: 300,
                    name: "Король природы",
                    difficulty: "Эксперт",
                    questions: 15,
                    categories: ['plants', 'animals', 'water', 'weather']
                }
            },
            
            // Инвентарь
            inventory: {
                water: 3,
                fertilizer: 2,
                seeds: 1
            },
            
            // Данные игрока
            player: {
                score: 0,
                correctAnswers: 0,
                questionsAnswered: 0,
                currentQuestion: 0,
                selectedAnswer: null
            },
            
            // Полные 60 вопросов (подходящие для начальной школы)
            categories: {
                plants: {
                    name: '🌱 Растения',
                    questions: [
                        {
                            question: 'Какой частью растения впитывается вода?',
                            options: ['Листья', 'Цветы', 'Корни', 'Плоды'],
                            correct: 2,
                            explanation: 'Корни растений действуют как соломинки, впитывая воду и питательные вещества из почвы.',
                            funFact: '🌱 Корни растений также прочно удерживают почву, предотвращая эрозию!'
                        },
                        {
                            question: 'Какая часть растения похожа на "пищевую фабрику"?',
                            options: ['Корни', 'Стебель', 'Листья', 'Цветы'],
                            correct: 2,
                            explanation: 'Листья производят пищу посредством фотосинтеза, для которого нужны солнечный свет, вода и воздух.',
                            funFact: '🍃 Без листьев растения остались бы голодными!'
                        },
                        {
                            question: 'Какое растение производит семена подсолнуха?',
                            options: ['Роза', 'Подсолнух', 'Кактус', 'Трава'],
                            correct: 1,
                            explanation: 'В центре цветка подсолнуха много маленьких семян - это те самые семечки, которые мы едим!',
                            funFact: '🌻 Головка подсолнуха следует за солнцем, поэтому его называют "подсолнухом"!'
                        },
                        {
                            question: 'Почему у кактусов много колючек?',
                            options: ['Для красоты', 'Для защиты от животных', 'Для впитывания воды', 'Для цветения'],
                            correct: 1,
                            explanation: 'Колючки кактуса - это видоизмененные листья, которые уменьшают испарение влаги.',
                            funFact: '🌵 Кактусы живут в пустыне, и их колючки также защищают от поедания животными!'
                        },
                        {
                            question: 'Какой фрукт растет на дереве?',
                            options: ['Арбуз', 'Клубника', 'Яблоко', 'Виноград'],
                            correct: 2,
                            explanation: 'Яблоки растут на яблонях и созревают осенью.',
                            funFact: '🍎 В каждом яблоке около 10 семян!'
                        },
                        {
                            question: 'Какой частью растения является морковь?',
                            options: ['Плод', 'Лист', 'Корень', 'Стебель'],
                            correct: 2,
                            explanation: 'Морковь - это корень растения, в котором хранится много питательных веществ.',
                            funFact: '🥕 Морковь бывает оранжевой, фиолетовой, желтой и многих других цветов!'
                        },
                        {
                            question: 'В какое время года листья желтеют и опадают?',
                            options: ['Весна', 'Лето', 'Осень', 'Зима'],
                            correct: 2,
                            explanation: 'Осенью становится холоднее, и листья перестают производить хлорофилл, поэтому желтеют и опадают.',
                            funFact: '🍂 Опавшие листья могут превращаться в удобрения, делая почву более плодородной!'
                        },
                        {
                            question: 'Какой тип дерева представляет собой сосна?',
                            options: ['Лиственное дерево', 'Вечнозеленое дерево', 'Дерево без листьев', 'Водное дерево'],
                            correct: 1,
                            explanation: 'Сосна - вечнозеленое дерево, у которого зеленые листья круглый год.',
                            funFact: '🎄 Листья сосны похожи на иголки, поэтому их называют хвойными деревьями!'
                        },
                        {
                            question: 'Откуда растения получают энергию?',
                            options: ['Из почвы', 'От солнечного света', 'От дождя', 'Из воздуха'],
                            correct: 1,
                            explanation: 'Растения преобразуют солнечный свет в энергию посредством фотосинтеза.',
                            funFact: '☀️ Солнце - самый важный источник энергии для всей жизни на Земле!'
                        },
                        {
                            question: 'Какое растение "ест" насекомых?',
                            options: ['Венерина мухоловка', 'Роза', 'Подсолнух', 'Трава'],
                            correct: 0,
                            explanation: 'Венерина мухоловка ловит маленьких насекомых и получает от них питательные вещества.',
                            funFact: '🪰 Венерина мухоловка закрывается очень быстро - всего за 0.1 секунды!'
                        },
                        {
                            question: 'Где растут бананы?',
                            options: ['На дереве', 'На земле', 'На лиане', 'В воде'],
                            correct: 0,
                            explanation: 'Бананы растут на банановых деревьях, хотя банановое дерево на самом деле является травянистым растением.',
                            funFact: '🍌 Банановое дерево плодоносит только один раз в жизни!'
                        },
                        {
                            question: 'Какова функция стебля растения?',
                            options: ['Впитывать воду', 'Производить пищу', 'Поддерживать растение', 'Цвести и плодоносить'],
                            correct: 2,
                            explanation: 'Стебель действует как "скелет" растения, поддерживая листья и цветы, а также транспортируя воду.',
                            funFact: '🌿 Стебли плюща имеют присоски, которые позволяют им карабкаться по стенам!'
                        },
                        {
                            question: 'Какой цветок ароматный и используется для изготовления духов?',
                            options: ['Подсолнух', 'Роза', 'Цветок кактуса', 'Трава'],
                            correct: 1,
                            explanation: 'Розы имеют приятный аромат и используются для изготовления духов и розового масла.',
                            funFact: '🌹 Розы разного цвета имеют разное значение!'
                        },
                        {
                            question: 'Где находятся семена у клубники?',
                            options: ['Внутри клубники', 'Снаружи клубники', 'На листьях', 'На корнях'],
                            correct: 1,
                            explanation: 'Семена клубники находятся снаружи мякоти - те самые маленькие точки и есть семена.',
                            funFact: '🍓 В одной клубнике около 200 семян!'
                        },
                        {
                            question: 'Какое растение может расти в воде?',
                            options: ['Лотос', 'Кактус', 'Сосна', 'Роза'],
                            correct: 0,
                            explanation: 'Лотос - водное растение, чьи корни растут в грязи на дне водоема.',
                            funFact: '🌸 Листья и цветы лотоса возвышаются над водой!'
                        }
                    ]
                },
                animals: {
                    name: '🐾 Животные',
                    questions: [
                        {
                            question: 'Какое животное откладывает яйца?',
                            options: ['Кошка', 'Собака', 'Курица', 'Кролик'],
                            correct: 2,
                            explanation: 'Птицы, рептилии и рыбы обычно откладывают яйца, в то время как млекопитающие рождают детенышей напрямую.',
                            funFact: '🥚 Страусиное яйцо - самое большое яйцо в мире!'
                        },
                        {
                            question: 'Кем является бабочка в детстве?',
                            options: ['Маленькая бабочка', 'Гусеница', 'Маленькая мушка', 'Маленькая пчела'],
                            correct: 1,
                            explanation: 'Бабочка проходит четыре стадии жизни: яйцо → гусеница → куколка → бабочка.',
                            funFact: '🦋 Некоторые гусеницы линяют 4-5 раз, прежде чем стать куколкой!'
                        },
                        {
                            question: 'Какое животное дышит жабрами?',
                            options: ['Щенок', 'Котенок', 'Рыбка', 'Птичка'],
                            correct: 2,
                            explanation: 'Рыбы используют жабры для получения кислорода из воды, так же как мы используем нос для дыхания воздухом.',
                            funFact: '🐠 Рыбы постоянно открывают рот, потому что дышат жабрами!'
                        },
                        {
                            question: 'Какое животное впадает в спячку зимой?',
                            options: ['Медведь', 'Обезьяна', 'Слон', 'Жираф'],
                            correct: 0,
                            explanation: 'Медведи спят зимой, почти не едят и не пьют - это называется спячкой.',
                            funFact: '🐻 Во время спячки сердцебиение медведя замедляется, а температура тела понижается!'
                        },
                        {
                            question: 'У какого животного длинная шея?',
                            options: ['Слон', 'Зебра', 'Жираф', 'Лев'],
                            correct: 2,
                            explanation: 'Жираф - самое высокое животное в мире, его шея длиной более 2 метров!',
                            funFact: '🦒 Язык жирафа синего цвета и длиной 45 сантиметров!'
                        },
                        {
                            question: 'Зачем пчелы собирают нектар?',
                            options: ['Для игры', 'Чтобы сделать мед', 'Для украшения улья', 'Чтобы подарить друзьям'],
                            correct: 1,
                            explanation: 'Пчелы приносят нектар в улей и превращают его в сладкий мед.',
                            funFact: '🍯 Пчеле нужно посетить 2000 цветков, чтобы сделать одну ложку меда!'
                        },
                        {
                            question: 'Какое животное меняет цвет?',
                            options: ['Кролик', 'Хамелеон', 'Панда', 'Пингвин'],
                            correct: 1,
                            explanation: 'Хамелеоны могут менять цвет кожи, чтобы прятаться или выражать эмоции.',
                            funFact: '🦎 Язык хамелеона длиннее его тела!'
                        },
                        {
                            question: 'Где живут детеныши кенгуру?',
                            options: ['На дереве', 'В норе', 'В сумке матери', 'У воды'],
                            correct: 2,
                            explanation: 'У мамы-кенгуру на животе есть сумка, где детеныш кенгуру растет.',
                            funFact: '🦘 Новорожденный кенгуренок размером с арахис!'
                        },
                        {
                            question: 'Где живут пингвины?',
                            options: ['В пустыне', 'В тропическом лесу', 'В Антарктиде', 'В горах'],
                            correct: 2,
                            explanation: 'Пингвины живут в холодной Антарктиде, у них толстый слой жира для тепла.',
                            funFact: '🐧 Пингвины не умеют летать, но отлично плавают!'
                        },
                        {
                            question: 'Какое животное называют "кораблем пустыни"?',
                            options: ['Лошадь', 'Верблюд', 'Осел', 'Овца'],
                            correct: 1,
                            explanation: 'Верблюды могут долгое время обходиться без воды в пустыне и помогают перевозить грузы.',
                            funFact: '🐫 В горбах верблюда хранится жир, а не вода!'
                        },
                        {
                            question: 'У какого животного черно-белые полосы?',
                            options: ['Зебра', 'Панда', 'Пингвин', 'Корова'],
                            correct: 0,
                            explanation: 'Черно-белые полосы зебры помогают им скрываться от хищников.',
                            funFact: '🦓 У каждой зебры уникальный рисунок полос!'
                        },
                        {
                            question: 'Какое животное лает?',
                            options: ['Кошка', 'Собака', 'Птица', 'Корова'],
                            correct: 1,
                            explanation: 'Собаки лают и являются друзьями человека.',
                            funFact: '🐶 У собаки 200 миллионов обонятельных клеток, что в 1000 раз больше, чем у человека!'
                        },
                        {
                            question: 'Какое животное мяукает?',
                            options: ['Собака', 'Кошка', 'Курица', 'Утка'],
                            correct: 1,
                            explanation: 'Кошки мяукают и любят ловить мышей.',
                            funFact: '🐱 Усы кошки измеряют ширину, помогая им определить, смогут ли они пройти!'
                        },
                        {
                            question: 'У какого животного длинный нос?',
                            options: ['Слон', 'Жираф', 'Бегемот', 'Носорог'],
                            correct: 0,
                            explanation: 'Нос слона, также называемый хоботом, может дышать, пить воду и брать предметы.',
                            funFact: '🐘 В хоботе слона 40 000 мышц!'
                        },
                        {
                            question: 'Какое животное носит свой дом на спине?',
                            options: ['Черепаха', 'Улитка', 'Краб', 'Еж'],
                            correct: 1,
                            explanation: 'Улитка носит свой панцирь и везде носит свой дом с собой.',
                            funFact: '🐌 Улитка - животное с наибольшим количеством зубов в мире, более 20 000!'
                        }
                    ]
                },
                water: {
                    name: '💧 Вода',
                    questions: [
                        {
                            question: 'Какие три состояния бывают у воды?',
                            options: ['Холодное, горячее, теплое', 'Чистое, грязное, мутное', 'Твердое, жидкое, газообразное', 'Сладкое, соленое, кислое'],
                            correct: 2,
                            explanation: 'Вода может быть льдом (твердое состояние), водой (жидкое состояние) и паром (газообразное состояние).',
                            funFact: '❄️ Лед плавает на воде, потому что он легче воды!'
                        },
                        {
                            question: 'В какую погоду идет дождь?',
                            options: ['Солнечная', 'Облачная', 'Дождливая', 'Снежная'],
                            correct: 2,
                            explanation: 'Маленькие капельки воды в облаках собираются вместе, становятся слишком тяжелыми и падают в виде дождя.',
                            funFact: '☁️ В каждом облаке тысячи маленьких капелек воды!'
                        },
                        {
                            question: 'Какой вкус у морской воды?',
                            options: ['Сладкий', 'Соленый', 'Кислый', 'Без вкуса'],
                            correct: 1,
                            explanation: 'В морской воде есть соль, поэтому она соленая. Реки приносят соль в море, вода испаряется, а соль остается.',
                            funFact: '🌊 Если разбросать всю соль из океанов по суше, получится слой высотой 150 метров!'
                        },
                        {
                            question: 'В какую погоду идет снег?',
                            options: ['Очень жаркая погода', 'Очень холодная погода', 'Ветреная погода', 'Туманная погода'],
                            correct: 1,
                            explanation: 'Когда очень холодно, капельки воды в облаках замерзают и превращаются в кристаллы льда, которые падают как снег.',
                            funFact: '❄️ В мире нет двух одинаковых снежинок!'
                        },
                        {
                            question: 'Во что превращается вода при кипении?',
                            options: ['Лед', 'Пар', 'Туман', 'Дождь'],
                            correct: 1,
                            explanation: 'При нагревании до 100°C вода превращается в пар, а видимый пар - это маленькие капельки воды.',
                            funFact: '💨 Водяной пар невидим, то, что мы видим как пар - это крошечные капельки воды!'
                        },
                        {
                            question: 'В какую погоду появляется радуга?',
                            options: ['После дождя, когда светит солнце', 'В снежную погоду', 'В ветреную погоду', 'В туманную погоду'],
                            correct: 0,
                            explanation: 'После дождя в воздухе много капелек воды, и солнечный свет, проходя через них, образует радугу.',
                            funFact: '🌈 В радуге семь цветов: красный, оранжевый, желтый, зеленый, голубой, синий, фиолетовый!'
                        },
                        {
                            question: 'Какое животное живет в воде?',
                            options: ['Птичка', 'Рыбка', 'Котенок', 'Щенок'],
                            correct: 1,
                            explanation: 'Рыбы дышат жабрами, поэтому могут жить только в воде.',
                            funFact: '🐟 Некоторые рыбы спят с открытыми глазами!'
                        },
                        {
                            question: 'Какое состояние воды представляет лед?',
                            options: ['Жидкое', 'Твердое', 'Газообразное', 'Плазменное'],
                            correct: 1,
                            explanation: 'Вода при температуре ниже 0°C замерзает и становится твердым льдом.',
                            funFact: '🧊 Мороженое тоже является формой льда, но с добавлением сахара и сливок!'
                        },
                        {
                            question: 'В какое время года больше всего дождей?',
                            options: ['Весна', 'Лето', 'Осень', 'Зима'],
                            correct: 1,
                            explanation: 'Летом температура высокая, вода испаряется быстрее, что приводит к образованию дождей.',
                            funFact: '🌧️ В некоторых местах летом дождь идет почти каждый день!'
                        },
                        {
                            question: 'Откуда берется водопроводная вода?',
                            options: ['Падает с неба', 'Появляется из крана', 'Приходит из очистных сооружений', 'Приходит прямо из моря'],
                            correct: 2,
                            explanation: 'Водопроводная вода берется из рек, водохранилищ, очищается и обеззараживается перед подачей в дома.',
                            funFact: '💧 Вода проходит много этапов обработки, прежде чем станет чистой водопроводной водой!'
                        },
                        {
                            question: 'В каком состоянии находится мороженое?',
                            options: ['Твердое', 'Жидкое', 'Газообразное', 'Полутвердое'],
                            correct: 3,
                            explanation: 'Мороженое - полутвердое вещество, содержащее кристаллы льда и жидкость.',
                            funFact: '🍦 Первое мороженое было изобретено в Китае 3000 лет назад!'
                        },
                        {
                            question: 'Для чего можно использовать воду?',
                            options: ['Пить', 'Мыть вещи', 'Поливать цветы', 'Все варианты'],
                            correct: 3,
                            explanation: 'У воды много применений: питье, приготовление пищи, стирка, полив цветов и т.д.',
                            funFact: '🚿 За один душ расходуется около 80 литров воды!'
                        },
                        {
                            question: 'Какой цвет указывает на чистую воду?',
                            options: ['Черный', 'Зеленый', 'Бесцветный прозрачный', 'Желтый'],
                            correct: 2,
                            explanation: 'Чистая вода бесцветна и прозрачна, не имеет цвета.',
                            funFact: '💎 Самая чистая вода прозрачна как кристалл!'
                        },
                        {
                            question: 'Что происходит со льдом в горячей воде?',
                            options: ['Увеличивается', 'Уменьшается', 'Тает', 'Замерзает'],
                            correct: 2,
                            explanation: 'Лед в горячей воде поглощает тепло и постепенно тает, превращаясь в воду.',
                            funFact: '🔥 Таяние льда требует поглощения тепла, поэтому лед охлаждает напитки!'
                        },
                        {
                            question: 'Как рыбы дышат под водой?',
                            options: ['Носом', 'Ртом', 'Жабры', 'Кожей'],
                            correct: 2,
                            explanation: 'Рыбы используют жабры для получения кислорода из воды и выделения углекислого газа.',
                            funFact: '🐡 Некоторые рыбы могут дышать даже через кожу!'
                        }
                    ]
                },
                weather: {
                    name: '☀️ Погода',
                    questions: [
                        {
                            question: 'Какая погода лучше всего подходит для запуска воздушного змея?',
                            options: ['Дождливая', 'Ветреная', 'Снежная', 'Туманная'],
                            correct: 1,
                            explanation: 'В ветреную погоду воздушный змей может взлететь, но если ветер слишком сильный, это может быть опасно.',
                            funFact: '🪁 Самый большой воздушный змей в мире размером с половину футбольного поля!'
                        },
                        {
                            question: 'В какую погоду нужно брать зонт?',
                            options: ['Солнечная', 'Облачная', 'Дождливая', 'Снежная'],
                            correct: 2,
                            explanation: 'В дождливую погоду зонт защищает от промокания.',
                            funFact: '☂️ Первый зонт был изобретен в Китае 3500 лет назад!'
                        },
                        {
                            question: 'Какая погода, когда светит солнце?',
                            options: ['Солнечная', 'Облачная', 'Дождливая', 'Снежная'],
                            correct: 0,
                            explanation: 'Погода, когда светит солнце, называется солнечной, она подходит для outdoor активностей.',
                            funFact: '☀️ Солнце - это звезда, вокруг которой вращается Земля!'
                        },
                        {
                            question: 'В какую погоду бывают гром и молния?',
                            options: ['Солнечная', 'Гроза', 'Снежная', 'Туманная'],
                            correct: 1,
                            explanation: 'Когда положительные и отрицательные заряды в облаках сталкиваются, возникают молния и гром.',
                            funFact: '⚡ Сначала видна молния, потом слышен гром, потому что свет быстрее звука!'
                        },
                        {
                            question: 'В какое время года самая жаркая погода?',
                            options: ['Весна', 'Лето', 'Осень', 'Зима'],
                            correct: 1,
                            explanation: 'Летом солнечные лучи падают прямо на северное полушарие, поэтому жарче всего.',
                            funFact: '🌡️ Самая высокая температура на Земле достигала 70°C!'
                        },
                        {
                            question: 'В какое время года самая холодная погода?',
                            options: ['Весна', 'Лето', 'Осень', 'Зима'],
                            correct: 3,
                            explanation: 'Зимой солнечные лучи падают наклонно на северное полушарие, поэтому холоднее всего.',
                            funFact: '🥶 Самая низкая температура в Антарктиде достигала -89.2°C!'
                        },
                        {
                            question: 'Какого цвета облака?',
                            options: ['Все белые', 'Все черные', 'Белые и серые', 'Разноцветные'],
                            correct: 2,
                            explanation: 'Тонкие облака белые, толстые - серые, очень толстые облака выглядят черными.',
                            funFact: '☁️ Облака на самом деле состоят из миллионов капелек воды или кристаллов льда!'
                        },
                        {
                            question: 'В какую погоду видно много звезд?',
                            options: ['Ясная ночь', 'Облачная ночь', 'Дождливая ночь', 'Снежная ночь'],
                            correct: 0,
                            explanation: 'В ясную ночь облаков нет, и можно видеть много звезд.',
                            funFact: '✨ Звезд на небе больше, чем песчинок на Земле!'
                        },
                        {
                            question: 'В какое время года дуют сильные ветры?',
                            options: ['Весна', 'Лето', 'Осень', 'Зима'],
                            correct: 0,
                            explanation: 'Весной холодные и теплые воздушные массы часто сменяют друг друга, что вызывает ветер.',
                            funFact: '💨 Скорость ветра в торнадо может достигать 500 км/ч!'
                        },
                        {
                            question: 'Что такое туман?',
                            options: ['Облака в небе', 'Облака у земли', 'Водяной пар', 'Пыль'],
                            correct: 1,
                            explanation: 'Туман - это облака, которые находятся близко к земле и состоят из множества капелек воды.',
                            funFact: '🌫️ При сильном тумане видимость очень низкая, и нужно включать противотуманные фары!'
                        },
                        {
                            question: 'Для чего нужен прогноз погоды?',
                            options: ['Угадать погоду', 'Научно предсказать погоду', 'Записать прошлую погоду', 'Изменить погоду'],
                            correct: 1,
                            explanation: 'Прогноз погоды использует научные методы для предсказания погоды на ближайшие дни.',
                            funFact: '📡 Метеорологические спутники в космосе помогают наблюдать за погодой!'
                        },
                        {
                            question: 'В какую погоду нужно носить теплую куртку?',
                            options: ['Летом', 'Зимой', 'Весной', 'Осенью'],
                            correct: 1,
                            explanation: 'Зимой температура низкая, и теплая куртка помогает согреться.',
                            funFact: '🧥 Пух в пуховике сохраняет воздух, который является хорошим теплоизолятором!'
                        },
                        {
                            question: 'В какую погоду зонт бесполезен?',
                            options: ['Дождливая', 'Снежная', 'Ветреная', 'Солнечная'],
                            correct: 3,
                            explanation: 'В солнечную погоду солнце светит, и не нужно защищаться от дождя зонтом.',
                            funFact: '⛱️ Но в солнечную погоду можно использовать зонт от солнца!'
                        },
                        {
                            question: 'В какую погоду нельзя плавать?',
                            options: ['Солнечная', 'Гроза', 'Облачная', 'Ветреная'],
                            correct: 1,
                            explanation: 'Плавать во время грозы опасно, потому что может ударить молния.',
                            funFact: '⚡ Вода проводит электричество, поэтому во время грозы нельзя находиться в воде!'
                        },
                        {
                            question: 'Как образуются времена года?',
                            options: ['Вращение Земли', 'Обращение Земли вокруг Солнца', 'Влияние Луны', 'Изменение размера Солнца'],
                            correct: 1,
                            explanation: 'Земля вращается вокруг Солнца, и в разное время солнечные лучи падают под разным углом, что создает времена года.',
                            funFact: '🌎 Полный оборот Земли вокруг Солнца - это один год!'
                        }
                    ]
                }
            }
        };

        // ===================== Инициализация игры =====================
        function initGame() {
            loadQuestion();
            updateDisplay();
            loadLevels();
            loadShop();
            updateFlowerDisplay();
            showNatureInfo("Добро пожаловать! Изучайте природные знания через вопросы и исследования. Нажимайте на объекты на картинке, чтобы узнать интересные факты!");
        }

        // ===================== Основные игровые функции =====================
        function selectCategory(category) {
            gameData.isLevelMode = false;
            gameData.currentCategory = category;
            gameData.player.currentQuestion = 0;
            gameData.player.selectedAnswer = null;
            
            document.querySelectorAll('.category-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            
            loadQuestion();
            
            const categoryName = gameData.categories[category].name;
            showNatureInfo(`Вы выбрали: ${categoryName}! Давайте изучать новые знания.`);
        }

        function loadQuestion() {
            const category = gameData.categories[gameData.currentCategory];
            const questions = category.questions;
            
            if (gameData.player.currentQuestion >= questions.length) {
                showCompletionMessage();
                return;
            }
            
            const question = questions[gameData.player.currentQuestion];
            
            // Показать вопрос
            document.getElementById('questionText').textContent = question.question;
            
            // Показать опции
            const optionsGrid = document.getElementById('optionsGrid');
            optionsGrid.innerHTML = '';
            
            question.options.forEach((option, index) => {
                const button = document.createElement('button');
                button.className = 'option-btn';
                button.textContent = option;
                button.onclick = () => selectAnswer(index);
                optionsGrid.appendChild(button);
            });
            
            // Сбросить состояние
            gameData.player.selectedAnswer = null;
            document.getElementById('submitBtn').disabled = true;
            document.getElementById('submitBtn').style.display = 'block';
            document.getElementById('nextBtn').style.display = 'none';
            document.getElementById('knowledgePanel').style.display = 'none';
            
            // Сбросить анимации
            document.querySelectorAll('.option-btn').forEach(btn => {
                btn.classList.remove('selected', 'correct-animation', 'incorrect-animation');
            });
        }

        function selectAnswer(index) {
            if (document.getElementById('nextBtn').style.display === 'block') return;
            
            document.querySelectorAll('.option-btn').forEach(btn => {
                btn.classList.remove('selected');
            });
            
            document.querySelectorAll('.option-btn')[index].classList.add('selected');
            gameData.player.selectedAnswer = index;
            document.getElementById('submitBtn').disabled = false;
        }

        function checkAnswer() {
            if (gameData.player.selectedAnswer === null) return;
            
            const category = gameData.categories[gameData.currentCategory];
            const question = category.questions[gameData.player.currentQuestion];
            const isCorrect = gameData.player.selectedAnswer === question.correct;
            
            gameData.player.questionsAnswered++;
            
            if (isCorrect) {
                gameData.player.score += 10;
                gameData.player.correctAnswers++;
                gameData.coins += 5; // Награда монетами
                updateCoinsDisplay();
                
                document.querySelectorAll('.option-btn')[gameData.player.selectedAnswer].classList.add('correct-animation');
                showKnowledgePanel("✅ Правильно!", question.explanation, question.funFact);
            } else {
                document.querySelectorAll('.option-btn')[gameData.player.selectedAnswer].classList.add('incorrect-animation');
                document.querySelectorAll('.option-btn')[question.correct].classList.add('correct-animation');
                showKnowledgePanel("❌ Попробуйте еще раз!", question.explanation, question.funFact);
            }
            
            updateDisplay();
            
            document.getElementById('submitBtn').style.display = 'none';
            document.getElementById('nextBtn').style.display = 'block';
            
            document.querySelectorAll('.option-btn').forEach(btn => {
                btn.style.pointerEvents = 'none';
            });
        }

        function nextQuestion() {
            gameData.player.currentQuestion++;
            gameData.player.selectedAnswer = null;
            
            document.querySelectorAll('.option-btn').forEach(btn => {
                btn.style.pointerEvents = 'auto';
            });
            
            loadQuestion();
        }

        function showKnowledgePanel(title, explanation, funFact) {
            const knowledgePanel = document.getElementById('knowledgePanel');
            const knowledgeTitle = document.getElementById('knowledgeTitle');
            const knowledgeContent = document.getElementById('knowledgeContent');
            
            knowledgeTitle.textContent = title;
            knowledgeContent.innerHTML = `
                <p><strong>📝 Объяснение:</strong> ${explanation}</p>
                <p style="margin-top: 15px; padding: 10px; background: #fffacd; border-radius: 10px; border-left: 4px solid #f1c40f;">
                    <strong>💡 Интересный факт:</strong> ${funFact}
                </p>
            `;
            
            knowledgePanel.style.display = 'block';
        }

        // ===================== Улучшенная система уровней =====================
        function loadLevels() {
            const levelsGrid = document.getElementById('levelsGrid');
            levelsGrid.innerHTML = '';
            
            for (let i = 1; i <= gameData.totalLevels; i++) {
                const level = gameData.levels[i];
                const levelCard = document.createElement('div');
                levelCard.className = 'level-card';
                
                if (!level.unlocked) {
                    levelCard.classList.add('locked');
                } else if (i === gameData.currentLevel && !level.completed) {
                    levelCard.classList.add('active');
                }
                
                levelCard.innerHTML = `
                    <div class="level-number">${i}</div>
                    <div style="font-size: 0.9em; margin-bottom: 5px;">${level.name}</div>
                    <div style="margin-bottom: 10px;">
                        ${level.completed ? '✅' : '🔒'}
                    </div>
                    <div class="level-reward">${level.reward} 🪙</div>
                `;
                
                if (level.unlocked) {
                    levelCard.onclick = () => startLevelGame(i);
                }
                
                levelsGrid.appendChild(levelCard);
            }
            
            updateLevelStats();
        }

        function startLevelGame(levelNumber) {
            gameData.isLevelMode = true;
            gameData.currentLevel = levelNumber;
            const level = gameData.levels[levelNumber];
            
            // Сбросить данные игрока
            gameData.player.score = 0;
            gameData.player.correctAnswers = 0;
            gameData.player.questionsAnswered = 0;
            gameData.player.currentQuestion = 0;
            gameData.player.selectedAnswer = null;
            
            // Сгенерировать вопросы для уровня
            generateLevelQuestions(levelNumber);
            
            // Переключиться на игровой интерфейс
            showGame();
            
            // Показать информацию об уровне
            showNatureInfo(`Уровень ${levelNumber}: ${level.name} (${level.difficulty})<br>Ответьте на ${level.questions} вопросов и выиграйте ${level.reward} монет!`);
            
            // Загрузить первый вопрос
            loadLevelQuestion();
        }

        function generateLevelQuestions(levelNumber) {
            const level = gameData.levels[levelNumber];
            gameData.currentLevelQuestions = [];
            
            // Выбрать вопросы для каждой категории
            level.categories.forEach(category => {
                const allQuestions = [...gameData.categories[category].questions];
                const questionsPerCategory = Math.ceil(level.questions / level.categories.length);
                
                // Случайный выбор вопросов
                for (let i = 0; i < questionsPerCategory && allQuestions.length > 0; i++) {
                    const randomIndex = Math.floor(Math.random() * allQuestions.length);
                    gameData.currentLevelQuestions.push({
                        ...allQuestions[randomIndex],
                        category: category
                    });
                    allQuestions.splice(randomIndex, 1); // Удалить выбранный вопрос
                }
            });
            
            // Если вопросов недостаточно, добавить еще
            while (gameData.currentLevelQuestions.length < level.questions && gameData.currentLevelQuestions.length > 0) {
                const randomQuestion = gameData.currentLevelQuestions[
                    Math.floor(Math.random() * gameData.currentLevelQuestions.length)
                ];
                gameData.currentLevelQuestions.push({...randomQuestion});
            }
            
            // Перемешать вопросы
            for (let i = gameData.currentLevelQuestions.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [gameData.currentLevelQuestions[i], gameData.currentLevelQuestions[j]] = 
                [gameData.currentLevelQuestions[j], gameData.currentLevelQuestions[i]];
            }
        }

        function loadLevelQuestion() {
            if (!gameData.isLevelMode || !gameData.currentLevelQuestions || 
                gameData.player.currentQuestion >= gameData.currentLevelQuestions.length) {
                completeLevel();
                return;
            }
            
            const question = gameData.currentLevelQuestions[gameData.player.currentQuestion];
            const level = gameData.levels[gameData.currentLevel];
            
            // Показать вопрос
            document.getElementById('questionText').textContent = question.question;
            
            // Показать опции
            const optionsGrid = document.getElementById('optionsGrid');
            optionsGrid.innerHTML = '';
            
            question.options.forEach((option, index) => {
                const button = document.createElement('button');
                button.className = 'option-btn';
                button.textContent = option;
                button.onclick = () => selectAnswer(index);
                optionsGrid.appendChild(button);
            });
            
            // Обновить счетчик вопросов
            const categoryName = gameData.categories[question.category].name;
            document.querySelector('.category-title').innerHTML = 
                `📚 Уровень ${gameData.currentLevel} | ${categoryName} | Вопрос ${gameData.player.currentQuestion + 1}/${level.questions}`;
            
            // Сбросить состояние
            gameData.player.selectedAnswer = null;
            document.getElementById('submitBtn').disabled = true;
            document.getElementById('submitBtn').style.display = 'block';
            document.getElementById('nextBtn').style.display = 'none';
            document.getElementById('knowledgePanel').style.display = 'none';
            
            // Сбросить анимации
            document.querySelectorAll('.option-btn').forEach(btn => {
                btn.classList.remove('selected', 'correct-animation', 'incorrect-animation');
            });
        }

        function completeLevel() {
            if (!gameData.isLevelMode) return;
            
            const level = gameData.levels[gameData.currentLevel];
            const accuracy = gameData.player.questionsAnswered > 0 ? 
                gameData.player.correctAnswers / gameData.player.questionsAnswered : 0;
            
            let stars = 0;
            if (accuracy >= 0.9) stars = 3;
            else if (accuracy >= 0.7) stars = 2;
            else if (accuracy >= 0.5) stars = 1;
            
            // Обновить статус уровня
            if (stars > level.stars) {
                level.stars = stars;
            }
            level.completed = true;
            
            // Рассчитать награду
            const bonus = stars * 20;
            const totalReward = level.reward + bonus;
            gameData.coins += totalReward;
            updateCoinsDisplay();
            
            // Разблокировать следующий уровень
            if (gameData.currentLevel < gameData.totalLevels) {
                gameData.levels[gameData.currentLevel + 1].unlocked = true;
            }
            
            // Показать сообщение о завершении
            document.getElementById('questionText').innerHTML = `
                <div style="text-align: center; padding: 30px;">
                    <h3 style="color: #27ae60; margin-bottom: 20px;">🎉 Поздравляем с прохождением!</h3>
                    <p>Вы прошли уровень ${gameData.currentLevel}: ${level.name}</p>
                    <p style="margin-top: 15px;">Точность: <strong>${Math.round(accuracy * 100)}%</strong></p>
                    <p>Получено звезд: <strong>${stars}/3 ⭐</strong></p>
                    <p>Получено монет: <strong>${totalReward} 🪙</strong></p>
                    <button onclick="showLevels()" style="margin-top: 20px; padding: 12px 25px; background: #3498db; color: white; border: none; border-radius: 10px; cursor: pointer;">
                        🏆 Вернуться к выбору уровней
                    </button>
                </div>
            `;
            
            document.getElementById('optionsGrid').innerHTML = '';
            document.getElementById('submitBtn').style.display = 'none';
            document.getElementById('nextBtn').style.display = 'none';
            
            // Обновить отображение уровней
            loadLevels();
            showNatureInfo(`🎉 Уровень ${gameData.currentLevel} пройден! Получено ${totalReward} монет, ${stars} звезд!`);
            
            // Выйти из режима уровней
            gameData.isLevelMode = false;
        }

        // Изменить функцию nextQuestion для поддержки режима уровней
        const originalNextQuestion = nextQuestion;
        nextQuestion = function() {
            if (gameData.isLevelMode) {
                gameData.player.currentQuestion++;
                gameData.player.selectedAnswer = null;
                
                document.querySelectorAll('.option-btn').forEach(btn => {
                    btn.style.pointerEvents = 'auto';
                });
                
                loadLevelQuestion();
            } else {
                originalNextQuestion();
            }
        };

        // Изменить функцию checkAnswer для поддержки режима уровней
        const originalCheckAnswer = checkAnswer;
        checkAnswer = function() {
            if (gameData.isLevelMode) {
                if (gameData.player.selectedAnswer === null) return;
                
                const question = gameData.currentLevelQuestions[gameData.player.currentQuestion];
                const isCorrect = gameData.player.selectedAnswer === question.correct;
                
                gameData.player.questionsAnswered++;
                
                if (isCorrect) {
                    gameData.player.score += 10;
                    gameData.player.correctAnswers++;
                    gameData.coins += 8; // В режиме уровней больше монет
                    updateCoinsDisplay();
                    
                    document.querySelectorAll('.option-btn')[gameData.player.selectedAnswer].classList.add('correct-animation');
                    showKnowledgePanel("✅ Правильно!", question.explanation, question.funFact);
                } else {
                    document.querySelectorAll('.option-btn')[gameData.player.selectedAnswer].classList.add('incorrect-animation');
                    document.querySelectorAll('.option-btn')[question.correct].classList.add('correct-animation');
                    showKnowledgePanel("❌ Попробуйте еще раз!", question.explanation, question.funFact);
                }
                
                updateDisplay();
                
                document.getElementById('submitBtn').style.display = 'none';
                document.getElementById('nextBtn').style.display = 'block';
                
                document.querySelectorAll('.option-btn').forEach(btn => {
                    btn.style.pointerEvents = 'none';
                });
            } else {
                originalCheckAnswer();
            }
        };

        function updateLevelStats() {
            let completed = 0;
            let totalCoins = 0;
            let totalStars = 0;
            
            for (let i = 1; i <= gameData.totalLevels; i++) {
                if (gameData.levels[i].completed) {
                    completed++;
                    totalCoins += gameData.levels[i].reward;
                    totalStars += gameData.levels[i].stars;
                }
            }
            
            document.getElementById('completedLevels').textContent = completed;
            document.getElementById('totalCoinsEarned').textContent = totalCoins;
            document.getElementById('totalStars').textContent = totalStars;
        }

        // ===================== Система монет и магазина =====================
        function updateCoinsDisplay() {
            document.getElementById('coinsCount').textContent = gameData.coins;
        }

        function loadShop() {
            const shopItems = document.getElementById('shopItems');
            shopItems.innerHTML = '';
            
            const items = [
                { id: 'water', name: 'Волшебная вода', desc: 'Полить цветок (+20% влаги)', price: 10, icon: '💧' },
                { id: 'fertilizer', name: 'Супер удобрение', desc: 'Ускорить рост цветка (+30%)', price: 20, icon: '🌿' },
                { id: 'seeds', name: 'Семена подсолнуха', desc: 'Новый цветок в саду', price: 50, icon: '🌻' },
                { id: 'rainbow', name: 'Радужный спрей', desc: 'Сделать цветок радужным!', price: 75, icon: '🌈' }
            ];
            
            items.forEach(item => {
                const canAfford = gameData.coins >= item.price;
                const shopItem = document.createElement('div');
                shopItem.className = 'shop-item';
                shopItem.innerHTML = `
                    <div class="shop-item-icon">${item.icon}</div>
                    <h4>${item.name}</h4>
                    <p style="font-size: 0.9em; color: #7f8c8d; margin: 10px 0;">${item.desc}</p>
                    <div class="shop-item-price">${item.price} 🪙</div>
                    <button class="buy-btn" onclick="buyItem('${item.id}', ${item.price})" 
                            ${!canAfford ? 'disabled' : ''}>
                        ${canAfford ? 'Купить' : 'Недостаточно монет'}
                    </button>
                `;
                shopItems.appendChild(shopItem);
            });
            
            updateInventoryDisplay();
        }

        function buyItem(itemId, price) {
            if (gameData.coins >= price) {
                gameData.coins -= price;
                updateCoinsDisplay();
                
                if (gameData.inventory[itemId]) {
                    gameData.inventory[itemId]++;
                } else {
                    gameData.inventory[itemId] = 1;
                }
                
                updateInventoryDisplay();
                loadShop();
                
                if (itemId === 'rainbow') {
                    gameData.flower.isRainbow = true;
                    applyRainbowEffect();
                    showNatureInfo("🌈 Ваш цветок теперь радужный! Он сияет всеми цветами радуги!");
                } else {
                    showNatureInfo(`✅ Куплено: ${itemId === 'water' ? 'вода' : 
                        itemId === 'fertilizer' ? 'удобрение' : 'семена'}!`);
                }
            }
        }

        function applyRainbowEffect() {
            const flowerHead = document.getElementById('flowerHead');
            if (flowerHead && gameData.flower.isRainbow) {
                flowerHead.classList.add('rainbow-flower');
            }
        }

        function updateInventoryDisplay() {
            const inventoryItems = document.getElementById('inventoryItems');
            inventoryItems.innerHTML = '';
            
            for (const [item, count] of Object.entries(gameData.inventory)) {
                if (count > 0) {
                    const itemDiv = document.createElement('div');
                    itemDiv.className = 'inventory-item';
                    
                    const icon = item === 'water' ? '💧' : 
                                item === 'fertilizer' ? '🌿' : 
                                item === 'seeds' ? '🌻' : '🌈';
                    
                    itemDiv.innerHTML = `
                        <span style="font-size: 1.5em;">${icon}</span>
                        <div>
                            <div style="font-weight: bold;">${item === 'water' ? 'Вода' : 
                             item === 'fertilizer' ? 'Удобрение' : 
                             item === 'seeds' ? 'Семена' : 'Радужный спрей'}</div>
                            <div style="font-size: 0.9em; color: #7f8c8d;">Количество: ${count}</div>
                        </div>
                    `;
                    inventoryItems.appendChild(itemDiv);
                }
            }
        }

        // ===================== Система цветов =====================
        function updateFlowerDisplay() {
            const flower = gameData.flower;
            
            const stemHeight = Math.min(150, flower.growth);
            document.getElementById('flowerStem').style.height = `${stemHeight}px`;
            
            if (flower.growth > 30) {
                const flowerSize = Math.min(50, (flower.growth - 30) * 2);
                const flowerHead = document.getElementById('flowerHead');
                flowerHead.style.width = `${flowerSize}px`;
                flowerHead.style.height = `${flowerSize}px`;
                flowerHead.style.opacity = '1';
                flowerHead.style.bottom = `${80 + stemHeight}px`;
                flowerHead.style.left = `calc(50% - ${flowerSize/2}px)`;
                
                applyRainbowEffect();
            }
            
            document.getElementById('waterStat').textContent = `${flower.water}%`;
            document.getElementById('fertilizerStat').textContent = `${flower.fertilizer}%`;
            document.getElementById('healthStat').textContent = `${flower.health}%`;
            
            document.getElementById('waterFill').style.width = `${flower.water}%`;
            document.getElementById('fertilizerFill').style.width = `${flower.fertilizer}%`;
            document.getElementById('healthFill').style.width = `${flower.health}%`;
        }

        function waterFlower() {
            if (gameData.inventory.water > 0) {
                gameData.inventory.water--;
                gameData.flower.water = Math.min(100, gameData.flower.water + 20);
                gameData.flower.growth += 5;
                updateFlowerDisplay();
                updateInventoryDisplay();
                showNatureInfo("💧 Цветок полит! Рост +5");
            } else {
                showNatureInfo("❌ Нет воды! Купите в магазине.");
            }
        }

        function fertilizeFlower() {
            if (gameData.inventory.fertilizer > 0) {
                gameData.inventory.fertilizer--;
                gameData.flower.fertilizer = Math.min(100, gameData.flower.fertilizer + 30);
                gameData.flower.growth += 10;
                updateFlowerDisplay();
                updateInventoryDisplay();
                showNatureInfo("🌿 Цветок удобрен! Рост +10");
            } else {
                showNatureInfo("❌ Нет удобрения! Купите в магазине.");
            }
        }

        // ===================== Навигация =====================
        function showGame() {
            document.getElementById('gameSection').style.display = 'grid';
            document.getElementById('levelsSection').style.display = 'none';
            document.getElementById('shopSection').style.display = 'none';
            document.getElementById('gardenSection').style.display = 'none';
        }

        function showLevels() {
            document.getElementById('gameSection').style.display = 'none';
            document.getElementById('levelsSection').style.display = 'block';
            document.getElementById('shopSection').style.display = 'none';
            document.getElementById('gardenSection').style.display = 'none';
            loadLevels();
        }

        function showShop() {
            document.getElementById('gameSection').style.display = 'none';
            document.getElementById('levelsSection').style.display = 'none';
            document.getElementById('shopSection').style.display = 'block';
            document.getElementById('gardenSection').style.display = 'none';
            loadShop();
        }

        function showGarden() {
            document.getElementById('gameSection').style.display = 'none';
            document.getElementById('levelsSection').style.display = 'none';
            document.getElementById('shopSection').style.display = 'none';
            document.getElementById('gardenSection').style.display = 'block';
            updateFlowerDisplay();
        }

        // ===================== Другие функции =====================
        function updateDisplay() {
            document.getElementById('score').textContent = gameData.player.score;
            document.getElementById('correctAnswers').textContent = gameData.player.correctAnswers;
            document.getElementById('questionsAnswered').textContent = gameData.player.questionsAnswered;
        }

        function showCompletionMessage() {
            document.getElementById('questionText').innerHTML = `
                <div style="text-align: center; padding: 30px;">
                    <h3 style="color: #27ae60; margin-bottom: 20px;">🎉 Поздравляем!</h3>
                    <p>Вы завершили все вопросы этой темы!</p>
                    <p style="margin-top: 15px;">Ваши очки: <strong>${gameData.player.score}</strong></p>
                    <p>Правильные ответы: <strong>${gameData.player.correctAnswers}/${gameData.player.questionsAnswered}</strong></p>
                    <button onclick="resetCategory()" style="margin-top: 20px; padding: 12px 25px; background: #3498db; color: white; border: none; border-radius: 10px; cursor: pointer;">
                        🔄 Играть снова
                    </button>
                </div>
            `;
            
            document.getElementById('optionsGrid').innerHTML = '';
            document.getElementById('submitBtn').style.display = 'none';
            document.getElementById('nextBtn').style.display = 'none';
        }

        function resetCategory() {
            gameData.player.currentQuestion = 0;
            gameData.player.selectedAnswer = null;
            loadQuestion();
        }

        function showPlantInfo() {
            const facts = [
                "🌻 Подсолнухи поворачиваются к солнцу в течение дня!",
                "🌳 Самому старому дереву на Земле более 4800 лет!",
                "🍃 Осенью листья меняют цвет, потому что хлорофилл распадается.",
                "🌱 Некоторые растения могут расти без почвы - только с водой!"
            ];
            
            const randomFact = facts[Math.floor(Math.random() * facts.length)];
            showNatureInfo(randomFact);
        }

        function showAnimalInfo() {
            const facts = [
                "🐇 Кролики могут вращать уши на 270 градусов!",
                "🦔 Ежи рождаются без иголок - они мягкие и белые.",
                "🦊 Лисы используют магнитное поле Земли для охоты!",
                "🐿️ Белки сажают тысячи деревьев каждый год, потому что забывают, где спрятали орехи."
            ];
            
            const randomFact = facts[Math.floor(Math.random() * facts.length)];
            showNatureInfo(randomFact);
        }

        function showWaterInfo() {
            const facts = [
                "💧 Тело человека на 60% состоит из воды!",
                "🌊 Вода - единственное вещество в природе, существующее в трех состояниях.",
                "❄️ Снежинки всегда имеют шесть сторон, но никогда не бывают одинаковыми.",
                "💦 Капля воды может находиться в океане до 3200 лет!"
            ];
            
            const randomFact = facts[Math.floor(Math.random() * facts.length)];
            showNatureInfo(randomFact);
        }

        function showTreeInfo() {
            const facts = [
                "🌳 Одно дерево может производить достаточно кислорода для 4 человек!",
                "🍂 Деревья общаются друг с другом через корневую систему.",
                "🎄 Самое высокое дерево - секвойя, высотой до 115 метров!",
                "🌲 Деревья замедляют рост зимой, но никогда не останавливаются полностью."
            ];
            
            const randomFact = facts[Math.floor(Math.random() * facts.length)];
            showNatureInfo(randomFact);
        }

        function showNatureInfo(message) {
            document.getElementById('natureDescription').innerHTML = `
                <strong>🔍 Интересный факт:</strong> ${message}
            `;
        }

        // ===================== Инициализация =====================
        window.onload = function() {
            initGame();
            
            setInterval(() => {
                if (gameData.flower.water > 0) gameData.flower.water -= 1;
                if (gameData.flower.fertilizer > 0) gameData.flower.fertilizer -= 0.5;
                
                if (gameData.flower.water < 30 || gameData.flower.fertilizer < 30) {
                    gameData.flower.health = Math.max(0, gameData.flower.health - 1);
                } else if (gameData.flower.health < 100) {
                    gameData.flower.health = Math.min(100, gameData.flower.health + 0.5);
                }
                
                updateFlowerDisplay();
            }, 30000);
        };
    </script>
</body>
</html>
