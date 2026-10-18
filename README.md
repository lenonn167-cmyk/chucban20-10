# chucban20-10
chucban20-10
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lời Chúc 20/10</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #0b0714;
            color: #ffffff;
            font-family: monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            text-align: center;
            -webkit-tap-highlight-color: transparent;
        }
        .card {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            cursor: pointer;
            padding: 20px;
            box-sizing: border-box;
        }
        .text {
            font-size: 22px;
            line-height: 1.6;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.7);
            animation: fadeIn 0.6s ease-in-out;
            z-index: 2;
            padding: 0 15px;
        }
        .instruction {
            position: absolute;
            bottom: 40px;
            font-size: 13px;
            color: #888;
            animation: pulse 1.5s infinite;
        }
        .eyes-container {
            display: flex;
            gap: 30px;
            margin-bottom: 30px;
            animation: fadeIn 0.6s ease-in-out;
        }
        .eye {
            width: 60px;
            height: 60px;
            background: #00ffff;
            border-radius: 15px;
            box-shadow: 0 0 20px #00ffff;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes pulse {
            0% { opacity: 0.3; }
            50% { opacity: 1; }
            100% { opacity: 0.3; }
        }
    </style>
</head>
<body>
    <div class="card" onclick="nextStep()">
        <div class="eyes-container" id="eyesContainer">
            <div class="eye"></div>
            <div class="eye"></div>
        </div>
        <div id="content" class="text">này cậu gì ơi</div>
        <div class="instruction">(Chạm vào màn hình để tiếp tục)</div>
    </div>

    <script>
        const steps = [
            { text: "này cậu gì ơi", showEyes: true },
            { text: "tớ là Tiny", showEyes: true },
            { text: "Hôm nay tớ nhận lệnh từ Dr X là để...", showEyes: true },
            { text: "ui cậu đẹp quá", showEyes: true },
            { text: "à thì cũng sắp 20/10 rồi", showEyes: false },
            { text: "nên là tớ muốn", showEyes: false },
            { text: "chúc cậu thật nhiều sức khỏe", showEyes: false },
            { text: "chúc cậu thật xinh đẹp", showEyes: false },
            { text: "và chúc cậu luôn giữ nụ cười trên môi", showEyes: false },
            { text: "tớ tặng cậu ngọn cỏ 4 lá này", showEyes: false },
            { text: "chúc cậu gặp thật nhiều điều may mắn ❤️", showEyes: false }
        ];

        let currentIndex = 0;
        const contentDiv = document.getElementById("content");
        const eyesContainer = document.getElementById("eyesContainer");

        function nextStep() {
            currentIndex++;
            if (currentIndex < steps.length) {
                contentDiv.style.animation = 'none';
                contentDiv.offsetHeight; 
                contentDiv.style.animation = 'fadeIn 0.6s ease-in-out';
                contentDiv.textContent = steps[currentIndex].text;

                if (steps[currentIndex].showEyes) {
                    eyesContainer.style.display = "flex";
                } else {
                    eyesContainer.style.display = "none";
                }
            } else {
                currentIndex = 0;
                contentDiv.textContent = steps[currentIndex].text;
                eyesContainer.style.display = "flex";
            }
        }
    </script>
</body>
</html>
