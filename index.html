<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>لغز الأرقام</title>
    <style>
        body {
            background-color: #000000; /* خلفية سوداء */
            color: #ecf0f1;
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 20px;
        }
        h2 { color: #2ecc71; }
        .hidden { display: none !important; }
        input {
            padding: 10px;
            font-size: 18px;
            text-align: center;
            border-radius: 5px;
            border: 2px solid #333;
            margin: 10px;
            width: 150px;
            background-color: #1a1a1a;
            color: white;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            background-color: #2ecc71;
            color: #000;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            margin: 5px;
        }
        button:hover { background-color: #27ae60; }
        .btn-undo { background-color: #3498db; color: white; }
        .btn-undo:hover { background-color: #2980b9; }
        .btn-reset { background-color: #f1c40f; color: #000; }
        
        .board-container {
            width: 100%;
            overflow-x: auto; /* سكرول أفقي عشان ما يخرب الشكل */
            padding-bottom: 15px;
            margin-top: 40px;
        }
        
        .board {
            display: flex;
            flex-wrap: nowrap; /* صف واحد */
            justify-content: flex-start;
            gap: 8px;
            width: max-content;
            margin: 0 auto;
            direction: ltr; /* من اليسار لليمين */
        }
        
        /* تجميل شكل السكرول */
        .board-container::-webkit-scrollbar { height: 10px; }
        .board-container::-webkit-scrollbar-track { background: #1a1a1a; border-radius: 5px; }
        .board-container::-webkit-scrollbar-thumb { background: #555; border-radius: 5px; }
        
        .cell {
            width: 45px;
            height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            border: 2px solid #333;
            color: #fff;
            transition: background-color 0.2s;
            flex-shrink: 0; /* يمنع المربعات من الانكماش */
        }
        .green { background-color: #2ecc71; }
        .red { background-color: #e74c3c; }
        
        #game-info {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
        }
        #message {
            margin-top: 30px;
            font-size: 28px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h2>لغز الأرقام العجيب 🧩</h2>

    <!-- شاشة إعداد اللعبة -->
    <div id="setup-section">
        <p>كم محاولة تبي تعطيهم قبل ما يخسرون؟</p>
        <input type="number" id="attempts-input" min="1" value="10">
        <br><br>
        <button onclick="startGame()">ابدأ اللعب</button>
    </div>

    <!-- شاشة اللعب -->
    <div id="game-section" class="hidden">
        <div id="game-info">
            المحاولات المتبقية: <span id="attempts-display" style="color: #e74c3c;">0</span>
        </div>
        
        <div class="board-container">
            <div class="board" id="board"></div>
        </div>
        
        <div id="message"></div>
        
        <br>
        <button onclick="undoMove()" class="btn-undo">تراجع ↩️</button>
        <button onclick="resetSetup()" class="btn-reset">إعادة ضبط 🔄</button>
    </div>

    <script>
        const sequence = [21, 20, 19, 18, 17, 16, 15, 14, 13, 12, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11];
        let state = [];
        let moveHistory = []; // مصفوفة لحفظ السجل عشان التراجع
        let maxAttempts = 0;
        let currentAttempts = 0;
        let isGameOver = false;

        function startGame() {
            let inputVal = document.getElementById('attempts-input').value;
            maxAttempts = parseInt(inputVal);
            
            if(isNaN(maxAttempts) || maxAttempts < 1) {
                alert("بديهياً حط رقم محاولات صاحي!");
                return;
            }

            currentAttempts = maxAttempts;
            isGameOver = false;
            moveHistory = []; // تصفير السجل مع كل لعبة جديدة
            
            document.getElementById('message').innerText = "";
            document.getElementById('attempts-display').innerText = currentAttempts;
            
            state = new Array(sequence.length).fill(true);
            state[9] = false; // رقم 12 أحمر
            state[11] = false; // رقم 2 أحمر

            document.getElementById('setup-section').classList.add('hidden');
            document.getElementById('game-section').classList.remove('hidden');

            renderBoard();
        }

        function renderBoard() {
            const board = document.getElementById('board');
            board.innerHTML = '';

            for(let i = 0; i < sequence.length; i++) {
                const cell = document.createElement('div');
                cell.className = 'cell ' + (state[i] ? 'green' : 'red');
                cell.innerText = sequence[i];
                cell.onclick = () => handleCellClick(i);
                board.appendChild(cell);
            }
        }

        function handleCellClick(index) {
            if(isGameOver) return;

            // حفظ الحالة الحالية في السجل قبل أي تغيير
            moveHistory.push({
                stateCopy: [...state],
                attemptsCopy: currentAttempts
            });

            // تغيير حالة المربع
            state[index] = !state[index];

            // الجار الأيسر
            if(index > 0) {
                state[index - 1] = !state[index - 1];
            }

            // الجار الأيمن
            if(index < state.length - 1) {
                state[index + 1] = !state[index + 1];
            }

            currentAttempts--;
            document.getElementById('attempts-display').innerText = currentAttempts;
            renderBoard();
            checkWinCondition();
        }

        function undoMove() {
            if(moveHistory.length === 0) {
                alert("ما فيه حركات سابقة تتراجع عنها يا كابتن!");
                return;
            }

            // استرجاع آخر حالة من السجل
            const lastMove = moveHistory.pop();
            state = [...lastMove.stateCopy];
            currentAttempts = lastMove.attemptsCopy;
            
            isGameOver = false; // لو كان خسران يتصفر اللعب
            document.getElementById('message').innerText = "";
            document.getElementById('attempts-display').innerText = currentAttempts;
            
            renderBoard();
        }

        function checkWinCondition() {
            const isWin = state.every(val => val === true);

            if(isWin) {
                isGameOver = true;
                document.getElementById('message').innerText = "🎉 ذيبان! حليتها!";
                document.getElementById('message').style.color = "#2ecc71";
            } else if (currentAttempts <= 0) {
                isGameOver = true;
                document.getElementById('message').innerText = "❌ خلصت محاولاتك يا فاشل!";
                document.getElementById('message').style.color = "#e74c3c";
            }
        }

        function resetSetup() {
            document.getElementById('game-section').classList.add('hidden');
            document.getElementById('setup-section').classList.remove('hidden');
        }
    </script>
</body>
</html>
