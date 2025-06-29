<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Чем заняться?</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            min-height: 100vh;
            font-family: Arial, sans-serif;
            background: url('https://a.imgfoto.host/2025/06/28/IZOBRAZENIE_2025-06-28_171920382.png') no-repeat center center;
            background-size: cover;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .wrapper {
            text-align: center;
        }

        #generateBtn {
            padding: 15px 25px;
            font-size: 18px;
            cursor: pointer;
            border: none;
            border-radius: 10px;
            background-color: rgba(72, 187, 120, 0.9);
            color: white;
            transition: background-color 0.3s, transform 0.2s;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        #generateBtn:hover {
            background-color: rgba(72, 187, 120, 1);
            transform: scale(1.05);
        }

        .popup {
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(255, 255, 255, 0.95);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            text-align: center;
            max-width: 80%;
        }

        .popup p {
            font-size: 18px;
            color: #333;
            margin-bottom: 15px;
        }

        .popup button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            border: none;
            border-radius: 8px;
            margin: 5px;
            transition: background-color 0.3s, transform 0.2s;
        }

        .popup button#generateMoreBtn {
            background-color: rgba(0, 172, 237, 0.9);
            color: white;
        }

        .popup button#generateMoreBtn:hover {
            background-color: rgba(0, 172, 237, 1);
            transform: scale(1.05);
        }

        .popup button#closeBtn {
            background-color: rgba(255, 99, 71, 0.9);
            color: white;
        }

        .popup button#closeBtn:hover {
            background-color: rgba(255, 99, 71, 1);
            transform: scale(1.05);
        }

        @media (max-width: 600px) {
            #generateBtn {
                padding: 12px 18px;
                font-size: 16px;
            }

            .popup {
                padding: 15px;
                max-width: 90%;
            }

            .popup p {
                font-size: 16px;
            }

            .popup button {
                padding: 8px 15px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <div class="wrapper">
        <button id="generateBtn">Чем заняться?</button>
    </div>

    <div class="popup" id="popup">
        <p id="result"></p>
        <button id="generateMoreBtn">Сгенерировать ещё</button>
        <button id="closeBtn">Закрыть</button>
    </div>

    <script>
        const places = ['парке', 'кафе', 'кино', 'музее', 'на пляже']; // Вставь свои места
        const actions = ['погулять', 'поесть', 'посмотреть фильм', 'почитать', 'потанцевать']; // Вставь свои действия

        const generateBtn = document.getElementById('generateBtn');
        const popup = document.getElementById('popup');
        const result = document.getElementById('result');
        const generateMoreBtn = document.getElementById('generateMoreBtn');
        const closeBtn = document.getElementById('closeBtn');

        function getRandomItem(array) {
            return array[Math.floor(Math.random() * array.length)];
        }

        function generateActivity() {
            const place = getRandomItem(places);
            const action = getRandomItem(actions);
            result.textContent = `${action} в ${place}`;
        }

        generateBtn.addEventListener('click', () => {
            generateActivity();
            popup.style.display = 'block';
        });

        generateMoreBtn.addEventListener('click', () => {
            generateActivity();
        });

        closeBtn.addEventListener('click', () => {
            popup.style.display = 'none';
        });
    </script>
</body>
</html>
