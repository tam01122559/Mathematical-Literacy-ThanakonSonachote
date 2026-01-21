<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์การเงิน ป.5</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    * {
      font-family: 'Prompt', sans-serif;
    }
    .coin-spin {
      animation: spin 1s ease-in-out;
    }
    @keyframes spin {
      0% { transform: rotateY(0deg); }
      100% { transform: rotateY(360deg); }
    }
    .bounce-in {
      animation: bounceIn 0.5s ease-out;
    }
    @keyframes bounceIn {
      0% { transform: scale(0); opacity: 0; }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); opacity: 1; }
    }
    .float {
      animation: float 3s ease-in-out infinite;
    }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    .sparkle {
      animation: sparkle 0.6s ease-out;
    }
    @keyframes sparkle {
      0% { transform: scale(0) rotate(0deg); opacity: 1; }
      100% { transform: scale(1.5) rotate(180deg); opacity: 0; }
    }
    .progress-fill {
      transition: width 0.5s ease-out;
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app-container" class="h-full overflow-auto" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 25%, #f093fb 50%, #4facfe 75%, #00f2fe 100%);"><!-- Header -->
   <header class="p-4 text-center relative">
    <div class="absolute top-4 right-4 flex items-center gap-2 bg-yellow-400 px-4 py-2 rounded-full shadow-lg"><span class="text-2xl">🪙</span> <span id="total-coins" class="text-purple-900 font-bold text-xl">0</span>
    </div>
    <h1 id="app-title" class="text-4xl md:text-5xl font-bold text-white drop-shadow-lg mb-2">คณิตศาสตร์การเงิน ป.5</h1>
    <p id="welcome-msg" class="text-white text-xl font-semibold drop-shadow">เรียนรู้เรื่องเงินอย่างสนุก! 💰</p>
   </header><!-- Main Menu -->
   <main id="main-menu" class="p-4 max-w-4xl mx-auto">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4"><!-- Module 1: น��บ���งิน --> <button onclick="startGame('counting')" class="group relative overflow-hidden rounded-2xl p-6 transition-all duration-300 hover:scale-105 hover:shadow-2xl" style="background: linear-gradient(135deg, #ff6b9d 0%, #ffa06e 100%);">
      <div class="absolute inset-0 bg-white/10 translate-y-full group-hover:translate-y-0 transition-transform duration-300"></div>
      <div class="relative z-10">
       <div class="text-6xl mb-4 float">
        🏦
       </div>
       <h2 class="text-2xl font-bold text-white mb-2 drop-shadow">นับเงิน</h2>
       <p class="text-white font-semibold">ฝึกนับธนบัตรและเหรียญ</p>
       <div class="mt-4 flex items-center gap-2"><span class="bg-white/30 px-3 py-1 rounded-full text-sm text-white font-bold">ระดับ 1-3</span>
       </div>
      </div></button> <!-- Module 2: ทอนเงิน --> <button onclick="startGame('change')" class="group relative overflow-hidden rounded-2xl p-6 transition-all duration-300 hover:scale-105 hover:shadow-2xl" style="background: linear-gradient(135deg, #00d2ff 0%, #3a7bd5 100%);">
      <div class="absolute inset-0 bg-white/10 translate-y-full group-hover:translate-y-0 transition-transform duration-300"></div>
      <div class="relative z-10">
       <div class="text-6xl mb-4 float">
        🛒
       </div>
       <h2 class="text-2xl font-bold text-white mb-2 drop-shadow">ทอนเงิน</h2>
       <p class="text-white font-semibold">คำนวณเงินทอนให้ถูกต้อง</p>
       <div class="mt-4 flex items-center gap-2"><span class="bg-white/30 px-3 py-1 rounded-full text-sm text-white font-bold">ระดับ 1-3</span>
       </div>
      </div></button> <!-- Module 3: ออมเงิน --> <button onclick="startGame('saving')" class="group relative overflow-hidden rounded-2xl p-6 transition-all duration-300 hover:scale-105 hover:shadow-2xl" style="background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);">
      <div class="absolute inset-0 bg-white/10 translate-y-full group-hover:translate-y-0 transition-transform duration-300"></div>
      <div class="relative z-10">
       <div class="text-6xl mb-4 float">
        🐷
       </div>
       <h2 class="text-2xl font-bold text-white mb-2 drop-shadow">ออมเงิน</h2>
       <p class="text-white font-semibold">วางแผนการออมเงิน</p>
       <div class="mt-4 flex items-center gap-2"><span class="bg-white/30 px-3 py-1 rounded-full text-sm text-white font-bold">ระดับ 1-3</span>
       </div>
      </div></button> <!-- Module 4: ซื้อของ --> <button onclick="startGame('shopping')" class="group relative overflow-hidden rounded-2xl p-6 transition-all duration-300 hover:scale-105 hover:shadow-2xl" style="background: linear-gradient(135deg, #fcb045 0%, #fd1d1d 50%, #833ab4 100%);">
      <div class="absolute inset-0 bg-white/10 translate-y-full group-hover:translate-y-0 transition-transform duration-300"></div>
      <div class="relative z-10">
       <div class="text-6xl mb-4 float">
        🎁
       </div>
       <h2 class="text-2xl font-bold text-white mb-2 drop-shadow">ซื้อของ</h2>
       <p class="text-white font-semibold">คำนวณราคาสินค้า</p>
       <div class="mt-4 flex items-center gap-2"><span class="bg-white/30 px-3 py-1 rounded-full text-sm text-white font-bold">ระดับ 1-3</span>
       </div>
      </div></button>
    </div><!-- Stats Section -->
    <div class="mt-8 bg-white/20 backdrop-blur-sm rounded-2xl p-6 shadow-xl">
     <h3 class="text-2xl font-bold text-white mb-4 flex items-center gap-2 drop-shadow">📊 สถิติของฉัน</h3>
     <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
      <div class="text-center p-4 bg-white/20 rounded-xl backdrop-blur shadow-lg">
       <div class="text-3xl mb-2">
        🎯
       </div>
       <div id="stat-correct" class="text-2xl font-bold text-green-600">
        0
       </div>
       <div class="text-white text-sm font-semibold">
        ��อบถูก
       </div>
      </div>
      <div class="text-center p-4 bg-white/20 rounded-xl backdrop-blur shadow-lg">
       <div class="text-3xl mb-2">
        🎮
       </div>
       <div id="stat-games" class="text-2xl font-bold text-blue-600">
        0
       </div>
       <div class="text-white text-sm font-semibold">
        เกมที่เล่น
       </div>
      </div>
      <div class="text-center p-4 bg-white/20 rounded-xl backdrop-blur shadow-lg">
       <div class="text-3xl mb-2">
        ⭐
       </div>
       <div id="stat-streak" class="text-2xl font-bold text-amber-500">
        0
       </div>
       <div class="text-white text-sm font-semibold">
        ตอบถูกติดต่อกัน
       </div>
      </div>
      <div class="text-center p-4 bg-white/20 rounded-xl backdrop-blur shadow-lg">
       <div class="text-3xl mb-2">
        🏆
       </div>
       <div id="stat-best" class="text-2xl font-bold text-purple-600">
        0
       </div>
       <div class="text-white text-sm font-semibold">
        ��ะแนนสูงสุด
       </div>
      </div>
     </div>
    </div>
   </main><!-- Game Screen -->
   <div id="game-screen" class="hidden p-4 max-w-2xl mx-auto">
    <div class="flex items-center justify-between mb-6"><button onclick="backToMenu()" class="flex items-center gap-2 text-white/80 hover:text-white transition-colors">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
      </svg> กลับ </button>
     <div class="flex items-center gap-4">
      <div class="text-white/80">
       ข้อ <span id="current-question" class="text-white font-bold">1</span>/10
      </div>
      <div class="flex items-center gap-2 bg-yellow-500/20 px-3 py-1 rounded-full"><span>🪙</span> <span id="game-coins" class="text-yellow-400 font-bold">0</span>
      </div>
     </div>
    </div><!-- Progress Bar -->
    <div class="h-3 bg-white/10 rounded-full mb-6 overflow-hidden">
     <div id="progress-bar" class="h-full bg-gradient-to-r from-green-400 to-emerald-500 progress-fill" style="width: 0%"></div>
    </div><!-- Question Area -->
    <div id="question-area" class="bg-white/10 backdrop-blur-sm rounded-2xl p-6 mb-6"><!-- Dynamic content -->
    </div><!-- Answer Area -->
    <div id="answer-area" class="space-y-4"><!-- Dynamic content -->
    </div><!-- Feedback -->
    <div id="feedback" class="hidden mt-6 p-4 rounded-xl text-center text-xl font-bold"></div>
   </div><!-- Result Screen -->
   <div id="result-screen" class="hidden p-4 max-w-md mx-auto text-center">
    <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-8">
     <div id="result-icon" class="text-8xl mb-4">
      🎉
     </div>
     <h2 id="result-title" class="text-3xl font-bold text-white mb-4">ยอดเยี่ยม!</h2>
     <p id="result-message" class="text-gray-300 mb-6">คุณทำได้ดีมาก!</p>
     <div class="grid grid-cols-2 gap-4 mb-6">
      <div class="bg-white/5 rounded-xl p-4">
       <div class="text-3xl mb-2">
        ✅
       </div>
       <div id="result-correct" class="text-2xl font-bold text-green-400">
        0
       </div>
       <div class="text-gray-400 text-sm">
        ตอบถูก
       </div>
      </div>
      <div class="bg-white/5 rounded-xl p-4">
       <div class="text-3xl mb-2">
        🪙
       </div>
       <div id="result-coins" class="text-2xl font-bold text-yellow-400">
        0
       </div>
       <div class="text-gray-400 text-sm">
        เหรียญที่ได้
       </div>
      </div>
     </div>
     <div class="flex gap-4"><button onclick="backToMenu()" class="flex-1 py-3 px-6 bg-white/10 hover:bg-white/20 text-white rounded-xl font-bold transition-colors"> กลับหน้าหลัก </button> <button onclick="playAgain()" class="flex-1 py-3 px-6 bg-gradient-to-r from-green-400 to-emerald-500 hover:from-green-500 hover:to-emerald-600 text-white rounded-xl font-bold transition-colors"> เล่นอีกครั้ง </button>
     </div>
    </div>
   </div>
  </div>
  <script>
    // Config
    const defaultConfig = {
      app_title: 'คณิตศาสตร���การเงิน ป.5',
      welcome_message: 'เรียนรู้��รื่องเงินอย่างสนุก!',
      primary_color: '#1a1a2e',
      accent_color: '#f5576c',
      text_color: '#ffffff',
      font_family: 'Prompt'
    };

    let config = { ...defaultConfig };

    // Game State
    let gameState = {
      currentGame: null,
      currentQuestion: 0,
      totalQuestions: 10,
      correctAnswers: 0,
      coins: 0,
      totalCoins: 0,
      streak: 0,
      bestStreak: 0,
      gamesPlayed: 0,
      totalCorrect: 0,
      questions: []
    };

    // Money Data
    const thaiMoney = {
      bills: [1000, 500, 100, 50, 20],
      coins: [10, 5, 2, 1],
      billEmojis: {
        1000: '💵',
        500: '💴',
        100: '💶',
        50: '💷',
        20: '💸'
      }
    };

    const products = [
      { name: 'ขนมปัง', emoji: '🍞', price: 25 },
      { name: 'นม', emoji: '🥛', price: 15 },
      { name: 'ไข่', emoji: '🥚', price: 12 },
      { name: 'แอปเปิ้ล', emoji: '🍎', price: 20 },
      { name: 'กล้วย', emoji: '🍌', price: 10 },
      { name: 'น้ำ', emoji: '💧', price: 7 },
      { name: 'ช็อกโกแลต', emoji: '🍫', price: 35 },
      { name: 'ไอศกรีม', emoji: '🍦', price: 30 },
      { name: 'คุกกี้', emoji: '🍪', price: 45 },
      { name: 'เค้ก', emoji: '🍰', price: 55 },
      { name: 'พิซซ่า', emoji: '🍕', price: 89 },
      { name: 'แฮมเบอร์เกอร์', emoji: '🍔', price: 65 },
      { name: 'ข��งเล่น', emoji: '🧸', price: 150 },
      { name: 'หนังสือ', emoji: '📚', price: 120 },
      { name: 'ดินสอ', emoji: '✏️', price: 8 }
    ];

    // Initialize SDK
    async function initSDK() {
      if (window.elementSdk) {
        window.elementSdk.init({
          defaultConfig,
          onConfigChange: async (newConfig) => {
            config = { ...defaultConfig, ...newConfig };
            updateUI();
          },
          mapToCapabilities: (cfg) => ({
            recolorables: [],
            borderables: [],
            fontEditable: undefined,
            fontSizeable: undefined
          }),
          mapToEditPanelValues: (cfg) => new Map([
            ['app_title', cfg.app_title || defaultConfig.app_title],
            ['welcome_message', cfg.welcome_message || defaultConfig.welcome_message]
          ])
        });
      }
    }

    function updateUI() {
      document.getElementById('app-title').textContent = config.app_title || defaultConfig.app_title;
      document.getElementById('welcome-msg').textContent = (config.welcome_message || defaultConfig.welcome_message) + ' 💰';
    }

    // Generate Questions
    function generateCountingQuestion(level) {
      let total = 0;
      let moneyItems = [];
      const billCount = level === 1 ? 2 : level === 2 ? 3 : 4;
      const coinCount = level === 1 ? 2 : level === 2 ? 3 : 4;

      for (let i = 0; i < billCount; i++) {
        const bill = thaiMoney.bills[Math.floor(Math.random() * (level + 1))];
        total += bill;
        moneyItems.push({ type: 'bill', value: bill });
      }

      for (let i = 0; i < coinCount; i++) {
        const coin = thaiMoney.coins[Math.floor(Math.random() * thaiMoney.coins.length)];
        total += coin;
        moneyItems.push({ type: 'coin', value: coin });
      }

      const wrongAnswers = [
        total + Math.floor(Math.random() * 50) + 10,
        total - Math.floor(Math.random() * 30) - 5,
        total + Math.floor(Math.random() * 100) + 50
      ].filter(a => a > 0 && a !== total);

      return {
        type: 'counting',
        moneyItems,
        correctAnswer: total,
        options: shuffle([total, ...wrongAnswers.slice(0, 3)])
      };
    }

    function generateChangeQuestion(level) {
      const product = products[Math.floor(Math.random() * products.length)];
      const payments = level === 1 ? [50, 100] : level === 2 ? [100, 500] : [500, 1000];
      const paid = payments[Math.floor(Math.random() * payments.length)];
      
      if (paid <= product.price) {
        return generateChangeQuestion(level);
      }

      const change = paid - product.price;
      const wrongAnswers = [
        change + Math.floor(Math.random() * 20) + 5,
        change - Math.floor(Math.random() * 15) - 3,
        paid - change
      ].filter(a => a > 0 && a !== change);

      return {
        type: 'change',
        product,
        paid,
        correctAnswer: change,
        options: shuffle([change, ...wrongAnswers.slice(0, 3)])
      };
    }

    function generateSavingQuestion(level) {
      const goals = [
        { name: 'ของเล่น', emoji: '🧸', price: level === 1 ? 100 : level === 2 ? 300 : 500 },
        { name: 'หนังสือ', emoji: '📚', price: level === 1 ? 150 : level === 2 ? 350 : 600 },
        { name: 'กระเป๋า', emoji: '🎒', price: level === 1 ? 200 : level === 2 ? 400 : 800 }
      ];
      const goal = goals[Math.floor(Math.random() * goals.length)];
      const dailySaving = level === 1 ? [10, 20] : level === 2 ? [20, 50] : [50, 100];
      const saving = dailySaving[Math.floor(Math.random() * dailySaving.length)];
      const days = Math.ceil(goal.price / saving);

      const wrongAnswers = [
        days + Math.floor(Math.random() * 5) + 1,
        days - Math.floor(Math.random() * 3) - 1,
        Math.floor(goal.price / (saving * 2))
      ].filter(a => a > 0 && a !== days);

      return {
        type: 'saving',
        goal,
        dailySaving: saving,
        correctAnswer: days,
        options: shuffle([days, ...wrongAnswers.slice(0, 3)])
      };
    }

    function generateShoppingQuestion(level) {
      const numItems = level === 1 ? 2 : level === 2 ? 3 : 4;
      const selectedProducts = [];
      const usedIndices = new Set();

      while (selectedProducts.length < numItems) {
        const idx = Math.floor(Math.random() * products.length);
        if (!usedIndices.has(idx)) {
          usedIndices.add(idx);
          selectedProducts.push({ ...products[idx], quantity: Math.floor(Math.random() * 3) + 1 });
        }
      }

      const total = selectedProducts.reduce((sum, p) => sum + p.price * p.quantity, 0);
      const wrongAnswers = [
        total + Math.floor(Math.random() * 30) + 10,
        total - Math.floor(Math.random() * 20) - 5,
        selectedProducts.reduce((sum, p) => sum + p.price, 0)
      ].filter(a => a > 0 && a !== total);

      return {
        type: 'shopping',
        products: selectedProducts,
        correctAnswer: total,
        options: shuffle([total, ...wrongAnswers.slice(0, 3)])
      };
    }

    function shuffle(array) {
      const arr = [...array];
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }
      return arr;
    }

    // Start Game
    function startGame(type) {
      gameState.currentGame = type;
      gameState.currentQuestion = 0;
      gameState.correctAnswers = 0;
      gameState.coins = 0;
      gameState.questions = [];

      for (let i = 0; i < gameState.totalQuestions; i++) {
        const level = i < 3 ? 1 : i < 7 ? 2 : 3;
        switch (type) {
          case 'counting':
            gameState.questions.push(generateCountingQuestion(level));
            break;
          case 'change':
            gameState.questions.push(generateChangeQuestion(level));
            break;
          case 'saving':
            gameState.questions.push(generateSavingQuestion(level));
            break;
          case 'shopping':
            gameState.questions.push(generateShoppingQuestion(level));
            break;
        }
      }

      document.getElementById('main-menu').classList.add('hidden');
      document.getElementById('game-screen').classList.remove('hidden');
      document.getElementById('result-screen').classList.add('hidden');
      
      showQuestion();
    }

    function showQuestion() {
      const q = gameState.questions[gameState.currentQuestion];
      document.getElementById('current-question').textContent = gameState.currentQuestion + 1;
      document.getElementById('game-coins').textContent = gameState.coins;
      document.getElementById('progress-bar').style.width = `${(gameState.currentQuestion / gameState.totalQuestions) * 100}%`;
      document.getElementById('feedback').classList.add('hidden');

      const questionArea = document.getElementById('question-area');
      const answerArea = document.getElementById('answer-area');

      switch (q.type) {
        case 'counting':
          questionArea.innerHTML = `
            <h3 class="text-xl font-bold text-white mb-4 text-center">💰 นับเงินทั้งหมดเท่าไหร่?</h3>
            <div class="flex flex-wrap justify-center gap-3">
              ${q.moneyItems.map(item => `
                <div class="bg-white/10 px-4 py-3 rounded-xl text-center bounce-in">
                  <div class="text-3xl mb-1">${item.type === 'bill' ? thaiMoney.billEmojis[item.value] : '🪙'}</div>
                  <div class="text-white font-bold">${item.value} บาท</div>
                </div>
              `).join('')}
            </div>
          `;
          break;

        case 'change':
          questionArea.innerHTML = `
            <h3 class="text-xl font-bold text-white mb-4 text-center">🛒 คำนวณเงินทอน</h3>
            <div class="text-center">
              <div class="text-6xl mb-4">${q.product.emoji}</div>
              <p class="text-white text-lg mb-2">${q.product.name} ราคา <span class="text-yellow-400 font-bold">${q.product.price}</span> บาท</p>
              <p class="text-gray-300">จ่ายด้วยธนบัตร <span class="text-green-400 font-bold">${q.paid}</span> บาท</p>
              <p class="text-white text-xl mt-4">ต้องทอนเงิ���เท่าไหร่?</p>
            </div>
          `;
          break;

        case 'saving':
          questionArea.innerHTML = `
            <h3 class="text-xl font-bold text-white mb-4 text-center">🐷 วางแผนการออม</h3>
            <div class="text-center">
              <div class="text-6xl mb-4">${q.goal.emoji}</div>
              <p class="text-white text-lg mb-2">อยากซื้อ${q.goal.name} ราคา <span class="text-yellow-400 font-bold">${q.goal.price}</span> บาท</p>
              <p class="text-gray-300">ถ้าออมวันละ <span class="text-green-400 font-bold">${q.dailySaving}</span> บาท</p>
              <p class="text-white text-xl mt-4">ต้องออมกี่วัน?</p>
            </div>
          `;
          break;

        case 'shopping':
          questionArea.innerHTML = `
            <h3 class="text-xl font-bold text-white mb-4 text-center">🛍️ รวมร������าสินค้า</h3>
            <div class="space-y-3">
              ${q.products.map(p => `
                <div class="flex items-center justify-between bg-white/10 px-4 py-3 rounded-xl">
                  <div class="flex items-center gap-3">
                    <span class="text-3xl">${p.emoji}</span>
                    <span class="text-white">${p.name}</span>
                  </div>
                  <div class="text-right">
                    <span class="text-gray-400">${p.price} × ${p.quantity} = </span>
                    <span class="text-yellow-400 font-bold">${p.price * p.quantity} บาท</span>
                  </div>
                </div>
              `).join('')}
            </div>
            <p class="text-white text-xl mt-4 text-center">รวมทั้งหมดเท่าไหร่?</p>
          `;
          break;
      }

      const unit = q.type === 'saving' ? 'วัน' : 'บาท';
      answerArea.innerHTML = `
        <div class="grid grid-cols-2 gap-4">
          ${q.options.map(opt => `
            <button onclick="checkAnswer(${opt})" class="py-4 px-6 bg-white/10 hover:bg-white/20 text-white text-xl font-bold rounded-xl transition-all hover:scale-105">
              ${opt} ${unit}
            </button>
          `).join('')}
        </div>
      `;
    }

    function checkAnswer(answer) {
      const q = gameState.questions[gameState.currentQuestion];
      const feedback = document.getElementById('feedback');
      const isCorrect = answer === q.correctAnswer;

      feedback.classList.remove('hidden');
      
      if (isCorrect) {
        gameState.correctAnswers++;
        gameState.coins += 10;
        gameState.streak++;
        if (gameState.streak > gameState.bestStreak) {
          gameState.bestStreak = gameState.streak;
        }
        feedback.className = 'mt-6 p-4 rounded-xl text-center text-xl font-bold bg-green-500/20 text-green-400';
        feedback.innerHTML = '✅ ถูกต้อง! +10 🪙';
        
        if (gameState.streak >= 3) {
          gameState.coins += 5;
          feedback.innerHTML += ` <br><span class="text-sm">🔥 ตอบถูกติดต่อกัน ${gameState.streak} ครั้ง! +5 โบ��ัส</span>`;
        }
      } else {
        gameState.streak = 0;
        const unit = q.type === 'saving' ? 'วัน' : 'บาท';
        feedback.className = 'mt-6 p-4 rounded-xl text-center text-xl font-bold bg-red-500/20 text-red-400';
        feedback.innerHTML = `❌ ไม่ถูกต้อง คำตอบคือ ${q.correctAnswer} ${unit}`;
      }

      document.getElementById('game-coins').textContent = gameState.coins;

      // Disable answer buttons
      document.querySelectorAll('#answer-area button').forEach(btn => {
        btn.disabled = true;
        btn.classList.add('opacity-50', 'cursor-not-allowed');
      });

      setTimeout(() => {
        gameState.currentQuestion++;
        if (gameState.currentQuestion < gameState.totalQuestions) {
          showQuestion();
        } else {
          showResult();
        }
      }, 1500);
    }

    function showResult() {
      gameState.totalCoins += gameState.coins;
      gameState.gamesPlayed++;
      gameState.totalCorrect += gameState.correctAnswers;

      document.getElementById('game-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.remove('hidden');

      const percentage = (gameState.correctAnswers / gameState.totalQuestions) * 100;
      let icon, title, message;

      if (percentage >= 90) {
        icon = '🏆';
        title = 'ยอดเยี่ยมมาก!';
        message = 'คุณเก่งมาก! เป็นนักคณิตศาสตร์ตัวจริง!';
      } else if (percentage >= 70) {
        icon = '🎉';
        title = 'ดีมาก!';
        message = 'คุณทำได้ดี! ลองเล่นอีกครั้งเพื่อพัฒนาต่อ!';
      } else if (percentage >= 50) {
        icon = '👍';
        title = 'ผ่า��ได้!';
        message = 'พยายามต่อไปน��! คุณทำได้ดีขึ้นแน่นอน!';
      } else {
        icon = '💪';
        title = 'ลองอีกครั้ง!';
        message = 'อย่าท้อ! ฝึกฝนบ่อยๆ จะเก่งขึ้นเอง!';
      }

      document.getElementById('result-icon').textContent = icon;
      document.getElementById('result-title').textContent = title;
      document.getElementById('result-message').textContent = message;
      document.getElementById('result-correct').textContent = `${gameState.correctAnswers}/${gameState.totalQuestions}`;
      document.getElementById('result-coins').textContent = gameState.coins;

      updateStats();
    }

    function updateStats() {
      document.getElementById('total-coins').textContent = gameState.totalCoins;
      document.getElementById('stat-correct').textContent = gameState.totalCorrect;
      document.getElementById('stat-games').textContent = gameState.gamesPlayed;
      document.getElementById('stat-streak').textContent = gameState.bestStreak;
      document.getElementById('stat-best').textContent = Math.max(
        gameState.correctAnswers,
        parseInt(document.getElementById('stat-best').textContent) || 0
      );
    }

    function backToMenu() {
      document.getElementById('main-menu').classList.remove('hidden');
      document.getElementById('game-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.add('hidden');
    }

    function playAgain() {
      startGame(gameState.currentGame);
    }

    // Initialize
    initSDK();
    updateUI();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c134278251a7323',t:'MTc2ODk2MTI2My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
