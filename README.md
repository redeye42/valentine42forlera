<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сюрприз для Леры</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #ffe4e1;
            margin-top: 50px;
        }
        h1 {
            font-size: 24px;
        }
        .gif-container {
            margin-bottom: 20px;
        }
        .gif {
            width: 250px;
            border-radius: 10px;
        }
        .container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }
        .button {
            width: 100px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            border: none;
            transition: all 0.3s ease;
        }
        .yes {
            background-color: green;
            color: white;
        }
        .no {
            background-color: red;
            color: white;
        }
        #message {
            font-size: 28px;
            display: none;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <!-- Гиф с котиками под заголовком -->
    <div class="gif-container" id="firstGif">
        <video class="gif" autoplay loop muted>
            <source src="https://files.catbox.moe/arhxxo.mp4" type="video/mp4">
        </video>
    </div>

    <h1>Лерочка, будешь ли ты моей валентинкой?</h1>

    <div class="container">
        <button class="button yes" id="yesButton">ДА</button>
        <button class="button no" id="noButton">НЕТ</button>
    </div>

    <h1 id="message">УРО 42 </h1>

    <!-- Гиф под финальным текстом -->
    <div class="gif-container" id="finalGif" style="display: none;">
        <video class="gif" autoplay loop muted>
            <source src="https://files.catbox.moe/3y1164.mp4" type="video/mp4">
        </video>
    </div>

    <script>
        let yesButton = document.getElementById("yesButton");
        let noButton = document.getElementById("noButton");
        let message = document.getElementById("message");
        let finalGif = document.getElementById("finalGif");
        let firstGif = document.getElementById("firstGif");
        let noMessages = ["Ты уверена?", "А может все-таки да?", "Подумай еще раз!", "Последний шанс!"];
        let noIndex = 0;
        let yesSize = 100;

        noButton.addEventListener("click", function() {
            if (noIndex < noMessages.length) {
                noButton.innerText = noMessages[noIndex];
                noIndex++;
            } else {
                noButton.style.display = "none";
            }
            yesSize += 30;
            yesButton.style.width = yesSize + "px";
            yesButton.style.height = yesSize / 2 + "px";
            yesButton.style.fontSize = yesSize / 5 + "px";
        });

        yesButton.addEventListener("click", function() {
            document.querySelector("h1").style.display = "none";
            document.querySelector(".container").style.display = "none";
            firstGif.style.display = "none"; // Скрываем первый гиф
            message.style.display = "block";
            finalGif.style.display = "block"; // Показываем второй гиф
        });
    </script>

</body>
</html>
