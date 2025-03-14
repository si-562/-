<!DOCTYPE html>
<html>
<head>
    <title>컬러 타로 카드 뽑기</title>
    <style>
        body { font-family: 'Arial', sans-serif; text-align: center; margin-top: 50px; }
        button { padding: 10px 20px; margin: 10px; cursor: pointer; }
        .card {
            display: inline-block;
            width: 100px;
            height: 150px;
            margin: 10px;
            border: 2px solid #ddd;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            line-height: 150px;
            font-weight: bold;
            color: #fff;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
        }
    </style>
</head>

<body>
    <h1>컬러 타로 카드 뽑기</h1>
    <button onclick="drawCard(1)">1장 뽑기</button>
    <button onclick="drawCard(3)">3장 뽑기</button>
    <div id="result"></div>

    <script>
        // 카드 데이터 구성
        const majorColors = ["red", "orange", "yellow", "green", "blue", "indigo", "violet"];
        const shades = ["light", "regular", "deep"];
        const minorColors = [
            "turquoise", "skyblue", "pink", "khaki", "brown", "ochre", "copper", "gray",
            "black", "white", "gold", "silver", "rainbow", "multicolor", "transparent",
            "opaque", "repeat", "duality"
        ];

        // 각 색상에 대한 실제 색상 코드 정의
        const colorCodes = {
            red: "#FF4C4C", orange: "#FFA500", yellow: "#FFEB3B", green: "#4CAF50",
            blue: "#2196F3", indigo: "#4B0082", violet: "#8A2BE2",
            turquoise: "#40E0D0", skyblue: "#87CEEB", pink: "#FFC0CB", khaki: "#C3B091",
            brown: "#8B4513", ochre: "#CC7722", copper: "#B87333", gray: "#808080",
            black: "#000000", white: "#FFFFFF", gold: "#FFD700", silver: "#C0C0C0",
            rainbow: "#E60073", multicolor: "#B0E0E6", transparent: "#E0FFFF",
            opaque: "#A9A9A9", repeat: "#7FFFD4", duality: "#5F9EA0"
        };

        // 덱 생성 (메이저 + 마이너, 각 색상당 2장씩 복제해서 78장 완성)
        let deck = [
            ...majorColors.flatMap(color => shades.map(shade => `${color}-${shade}`)),
            ...minorColors
        ];
        deck = [...deck, ...deck];

        // 카드 섞기
        function shuffle(deck) {
            for (let i = deck.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [deck[i], deck[j]] = [deck[j], deck[i]];
            }
        }

        // 카드 뽑기 함수
        function drawCard(num) {
            shuffle(deck);
            const drawnCards = deck.slice(0, num);
            const resultDiv = document.getElementById('result');
            resultDiv.innerHTML = "";

            // 뽑은 카드들 표시
            drawnCards.forEach(card => {
                const color = card.split("-")[0];
                const cardElement = document.createElement("div");
                cardElement.className = "card";
                cardElement.style.backgroundColor = colorCodes[color] || "#ddd";
                cardElement.innerText = card;
                resultDiv.appendChild(cardElement);
            });
        }
    </script>
</body>
</html>
