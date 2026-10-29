<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Приглашение на нашу свадьбу</title>
    <style>
        :root {
            /* Переменные цветов */
            --text-color: #222222;
            --accent-color: #9c27b0; /* Фиолетовый акцент для контраста с красным */
            --accent-hover: #7b1fa2;
            /* Белый полупрозрачный фон для карточек, чтобы текст читался поверх ковра */
            --card-bg: rgba(255, 255, 255, 0.92); 
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Georgia', serif;
            color: var(--text-color);
            line-height: 1.6;
            text-align: center;
            
            /* НАСТРОЙКА КОВРОВОГО ФОНА */
            /* Замените ссылку ниже на свою, когда загрузите картинку на хостинг */
            background-image: url("IMG_7198.JPG"); 
            background-attachment: scroll; /* Фон не прокручивается */
            background-position: center;
            background-size: cover;
            padding: 20px 10px;
        }

        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px 0;
        }

        /* Полупрозрачная шапка поверх ковра */
        header {
            background: var(--card-bg);
            padding: 40px 20px;
            border-radius: 12px;
            margin-bottom: 30px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.15);
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            font-weight: normal;
        }

        .date-main {
            font-size: 1.5rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            color: #b71c1c; /* Глубокий красный под цвет ковра */
            font-weight: bold;
        }

        /* Стили информационных блоков */
        section {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.15);
            margin-bottom: 30px;
            backdrop-filter: blur(4px); /* Эффект матового стекла */
        }

        /* Стили Таймера */
        .timer-container h3 {
            font-weight: normal;
            margin-bottom: 20px;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 1px;
        }

        .countdown {
            display: flex;
            justify-content: space-around;
            max-width: 400px;
            margin: 0 auto;
        }

        .countdown-item {
            display: flex;
            flex-direction: column;
        }

        .countdown-time {
            font-size: 2.2rem;
            font-weight: bold;
            color: #b71c1c;
        }

        .countdown-label {
            font-size: 0.8rem;
            color: #555;
        }

        /* Стили Формы RSVP */
        form {
            display: flex;
            flex-direction: column;
            text-align: left;
        }

        label {
            margin-top: 15px;
            font-weight: bold;
            font-size: 0.9rem;
        }

        input[type="text"] {
            width: 100%;
            padding: 12px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 6px;
            font-family: inherit;
            background: #fff;
        }

        .radio-group {
            margin-top: 8px;
        }

        .radio-option {
            display: block;
            margin-bottom: 8px;
            cursor: pointer;
        }

        button {
            margin-top: 25px;
            background-color: #b71c1c; /* Кнопка в тон ковра */
            color: white;
            border: none;
            padding: 15px;
            font-size: 1rem;
            border-radius: 6px;
            cursor: pointer;
            font-family: inherit;
            transition: background 0.2s;
            font-weight: bold;
            box-shadow: 0 4px 12px rgba(183, 28, 28, 0.3);
        }

        button:hover {
            background-color: #800000;
        }

        #form-status {
            margin-top: 15px;
            font-weight: bold;
            text-align: center;
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- Главный экран -->
        <header>
            <h1>Александр & Мария</h1>
            <p style="font-size: 1.1rem; color: #555;">Приглашают вас на ковровую вечеринку года!</p>
            <div class="date-main" style="margin-top: 20px;">18.07.2027</div>
        </header>

        <!-- Блок с деталями -->
        <section>
            <h2>Дорогие близкие и друзья!</h2>
            <p style="margin-top: 15px;">В нашей жизни наступает особенный момент. Мы будем счастливы разделить с вами этот незабываемый день!</p>
            <p style="margin-top: 15px;"><strong>Место:</strong> г. Москва, ресторан "Шале", ул. Лесная, 15</p>
            <p><strong>Сбор гостей:</strong> в 16:00</p>
        </section>

        <!-- БЛОК ТАЙМЕРА -->
        <section class="timer-container">
            <h3>До торжества осталось:</h3>
            <div class="countdown">
                <div class="countdown-item">
                    <span class="countdown-time" id="days">00</span>
                    <span class="countdown-label">дней</span>
                </div>
                <div class="countdown-item">
                    <span class="countdown-time" id="hours">00</span>
                    <span class="countdown-label">часов</span>
                </div>
                <div class="countdown-item">
                    <span class="countdown-time" id="minutes">00</span>
                    <span class="countdown-label">минут</span>
                </div>
                <div class="countdown-item">
                    <span class="countdown-time" id="seconds">00</span>
                    <span class="countdown-label">секунд</span>
                </div>
            </div>
        </section>

        <!-- БЛОК ФОРМЫ (RSVP) -->
        <section>
            <h2>Подтвердите присутствие</h2>
            <p style="font-size: 0.9rem; color: #666; margin-bottom: 15px;">Пожалуйста, ответьте до 18 июня 2027 года</p>
            
            <form id="rsvp-form">
                <label for="guest-name">Ваше имя и фамилия:</label>
                <input type="text" id="guest-name" placeholder="Иван и Ольга Ивановы" required>

                <label>Сможете ли вы прийти?</label>
                <div class="radio-group">
                    <label class="radio-option">
                        <input type="radio" name="attendance" value="Да, с удовольствием приду" checked> Я/Мы придем
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="attendance" value="К сожалению, не смогу"> Не смогу прийти
                    </label>
                </div>

                <label>Что вы предпочитаете из напитков?</label>
                <div class="radio-group">
                    <label class="radio-option">
                        <input type="checkbox" name="drinks" value="Красное вино"> Красное вино
                    </label>
                    <label class="radio-option">
                        <input type="checkbox" name="drinks" value="Белое вино"> Белое вино
                    </label>
                    <label class="radio-option">
                        <input type="checkbox" name="drinks" value="Крепкий алкоголь"> Крепкий алкоголь
                    </label>
                    <label class="radio-option">
                        <input type="checkbox" name="drinks" value="Безалкогольные"> Только безалкогольные
                    </label>
                </div>

                <button type="submit">Отправить ответ</button>
                <p id="form-status"></p>
            </form>
        </section>
    </div>

    <script>
        // Код исправленного стабильного таймера
        const weddingDate = new Date("07/18/2027 16:00:00").getTime();

        const timerInterval = setInterval(function() {
            const now = new Date().getTime();
            const distance = weddingDate - now;

            if (distance < 0) {
                clearInterval(timerInterval);
                document.querySelector(".timer-container").innerHTML = "<h3>Этот счастливый день настал!</h3>";
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerText = days < 10 ? "0" + days : days;
            document.getElementById("hours").innerText = hours < 10 ? "0" + hours : hours;
            document.getElementById("minutes").innerText = minutes < 10 ? "0" + minutes : minutes;
            document.getElementById("seconds").innerText = seconds < 10 ? "0" + seconds : seconds;
        }, 1000);

        // Код отправки в Telegram
        const TELEGRAM_BOT_TOKEN = 'ВАШ_ТОКЕН_БОТА'; 
        const TELEGRAM_CHAT_ID = 'ВАШ_ID_ЧАТА_ИЛИ_ПОЛЬЗОВАТЕЛЯ'; 

        document.getElementById('rsvp-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const statusText = document.getElementById('form-status');
            statusText.innerText = "Отправка...";
            statusText.style.color = "orange";

            const name = document.getElementById('guest-name').value;
