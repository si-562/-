<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>운의 수레바퀴 스프레드</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f8f4f9;
            color: #333;
        }
        .container {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        textarea {
            width: 100%;
            height: 50px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 10px;
        }
        button {
            background-color: #a78bfa;
            color: white;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 10px;
            margin-top: 20px;
        }
        .card {
            width: 100%;
            height: 100px;
            background: #e6d6f5;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            font-weight: bold;
            color: #5a3d8a;
            cursor: pointer;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            color: #5a3d8a;
        }
    </style>
</head>
<body>

    <div class="container">
        <h2>운의 수레바퀴 스프레드</h2>
        <p>질문을 입력하세요:</p>
        <textarea id="question" placeholder="여기에 질문을 입력하세요..."></textarea>
        <button onclick="shuffleCards()">카드 섞기</button>
        
        <div class="grid" id="cardContainer"></div>

        <p class="result" id="resultText"></p>
    </div>

    <script>
        function shuffleCards() {
            let cards = ["운명의 수레바퀴", "카드 1", "카드 2", "카드 3", "카드 4", "카드 5", "카드 6", "카드 7"];
            
            // 카드 섞기
            cards = cards.sort(() => Math.random() - 0.5);

            // 카드 표시
            let cardContainer = document.getElementById("cardContainer");
            cardContainer.innerHTML = "";
            cards.forEach((card, index) => {
                let cardElement = document.createElement("div");
                cardElement.className = "card";
                cardElement.textContent = card;
                cardContainer.appendChild(cardElement);
            });

            // 운명의 수레바퀴 위치 찾기
            let position = cards.indexOf("운명의 수레바퀴") + 1;
            let resultText = document.getElementById("resultText");

            // 위치에 따른 해석
            if (position === 1 || position === 5) {
                resultText.textContent = "결과: YES";
            } else if (position === 2 || position === 6) {
                resultText.textContent = "결과: SOON YES";
            } else if (position === 3 || position === 7) {
                resultText.textContent = "결과: MAYBE NO";
            } else if (position === 4 || position === 8) {
                resultText.textContent = "결과: NO";
            }
        }
    </script>

</body>
</html>
