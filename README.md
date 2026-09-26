<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Rock Paper Scissors Game</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #667eea, #764ba2);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .game {
            width: 90%;
            max-width: 500px;
            background: white;
            padding: 30px;
            border-radius: 25px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        h1 {
            color: #333;
            margin-bottom: 25px;
        }

        .computer-box {
            background: #f1f1f1;
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 25px;
        }

        .computer-box h2 {
            margin: 0 0 10px;
            font-size: 20px;
        }

        #computerChoice {
            font-size: 25px;
            font-weight: bold;
            color: #673ab7;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        button {
            border: none;
            padding: 15px 25px;
            font-size: 18px;
            font-weight: bold;
            color: white;
            border-radius: 12px;
            cursor: pointer;
            transition: 0.2s;
        }

        button:hover {
            transform: scale(1.08);
        }

        .rock {
            background: #2196F3;
        }

        .paper {
            background: #4CAF50;
        }

        .scissors {
            background: #F44336;
        }

        #result {
            margin-top: 30px;
            font-size: 28px;
            font-weight: bold;
            min-height: 35px;
        }

        .win {
            color: green;
        }

        .lose {
            color: red;
        }

        .tie {
            color: orange;
        }

        .reset {
            margin-top: 20px;
            background: #333;
            font-size: 16px;
        }
    </style>
</head>

<body>

    <div class="game">

        <h1>🎮 ROCK PAPER SCISSORS</h1>

        <div class="computer-box">
            <h2>COMPUTER CHOICE</h2>
            <div id="computerChoice">---</div>
        </div>

        <h2>Choose Your Option</h2>

        <div class="buttons">
            <button class="rock" onclick="playGame('ROCK')">
                🪨 ROCK
            </button>

            <button class="paper" onclick="playGame('PAPER')">
                📄 PAPER
            </button>

            <button class="scissors" onclick="playGame('SCISSORS')">
                ✂️ SCISSORS
            </button>
        </div>

        <div id="result"></div>

        <button class="reset" onclick="resetGame()">
            🔄 RESET
        </button>

    </div>


    <script>

        // Same list as your MIT App Inventor program
        const choices = ["ROCK", "PAPER", "SCISSORS"];


        function playGame(playerChoice) {

            // Computer randomly chooses
            const computerChoice =
                choices[Math.floor(Math.random() * choices.length)];


            // Display computer choice
            document.getElementById("computerChoice").textContent =
                computerChoice;


            let result = "";
            let resultClass = "";


            // ROCK
            if (playerChoice === "ROCK") {

                if (computerChoice === "SCISSORS") {
                    result = "YOU WIN!";
                    resultClass = "win";
                }

                else if (computerChoice === "PAPER") {
                    result = "YOU LOSE!";
                    resultClass = "lose";
                }

                else {
                    result = "IT'S A TIE!";
                    resultClass = "tie";
                }
            }


            // PAPER
            else if (playerChoice === "PAPER") {

                if (computerChoice === "ROCK") {
                    result = "YOU WIN!";
                    resultClass = "win";
                }

                else if (computerChoice === "SCISSORS") {
                    result = "YOU LOSE!";
                    resultClass = "lose";
                }

                else {
                    result = "IT'S A TIE!";
                    resultClass = "tie";
                }
            }


            // SCISSORS
            else if (playerChoice === "SCISSORS") {

                if (computerChoice === "PAPER") {
                    result = "YOU WIN!";
                    resultClass = "win";
                }

                else if (computerChoice === "ROCK") {
                    result = "YOU LOSE!";
                    resultClass = "lose";
                }

                else {
                    result = "IT'S A TIE!";
                    resultClass = "tie";
                }
            }


            // Display result
            const resultBox = document.getElementById("result");

            resultBox.textContent = result;

            resultBox.className = resultClass;
        }


        // Reset game
        function resetGame() {

            document.getElementById("computerChoice").textContent = "---";

            document.getElementById("result").textContent = "";

            document.getElementById("result").className = "";
        }

    </script>

</body>
</html>
