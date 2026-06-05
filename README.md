[index.html](https://github.com/user-attachments/files/28651059/index.html)
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>HQ CLAN | BRM5</title>
</head>
<body style="background-color: #0A0B0C; color: #E2E8F0; font-family: 'Courier New', Courier, monospace; margin: 0; padding: 0; text-align: center;">

    <div style="max-width: 600px; margin: 0 auto; padding: 40px 20px;">
        <h1 style="font-size: 2.5rem; color: #00FF41; letter-spacing: 2px; margin-bottom: 5px;">АНКЕТА НА РЯДОВОГО</h1>
        <div style="color: #888; font-size: 1.1rem; margin-bottom: 30px;">Тактическое подразделение Blackhawk Rescue Mission 5</div>
        
        <p style="margin-bottom: 25px;">Мы ведем набор активных, адекватных и дисциплинированных бойцов. Ждем тебя.</p>
        
        <a href="https://discord.gg" target="_blank" style="display: inline-block; background-color: #4C704C; color: #fff; padding: 12px 25px; text-decoration: none; font-weight: bold; border: 2px solid #00FF41; text-transform: uppercase; margin-bottom: 40px;">Войти в Discord Клана</a>

        <div style="background-color: #111411; border: 1px dashed #4C704C; padding: 25px; text-align: left;">
            <h2 style="color: #00FF41; margin-top: 0; font-size: 1.5rem; text-transform: uppercase;">ЗАПОЛНИТЕ ФОРМУ</h2>
            <p style="color: #888; font-size: 0.9rem; margin-bottom: 20px;">Офицеры рассмотрят заявку прямо на сервере.</p>
            
            <form id="clanForm">
                <div style="margin-bottom: 15px;">
                    <label style="display: block; margin-bottom: 5px; font-weight: bold;">Ваш ник в Roblox:</label>
                    <input type="text" id="robloxNick" placeholder="Например: RobloxPlayer123" required style="width: 100%; padding: 10px; background-color: #0A0B0C; border: 1px solid #4C704C; color: #00FF41; box-sizing: border-box; font-family: inherit;">
                </div>

                <div style="margin-bottom: 15px;">
                    <label style="display: block; margin-bottom: 5px; font-weight: bold;">Ваш Discord ID (Имя пользователя):</label>
                    <input type="text" id="discordId" placeholder="Например: sniper_brm5" required style="width: 100%; padding: 10px; background-color: #0A0B0C; border: 1px solid #4C704C; color: #00FF41; box-sizing: border-box; font-family: inherit;">
                </div>

                <div style="margin-bottom: 15px;">
                    <label style="display: block; margin-bottom: 5px; font-weight: bold;">Ваш возраст:</label>
                    <input type="number" id="age" min="10" max="99" placeholder="14" required style="width: 100%; padding: 10px; background-color: #0A0B0C; border: 1px solid #4C704C; color: #00FF41; box-sizing: border-box; font-family: inherit;">
                </div>

                <div style="margin-bottom: 15px;">
                    <label style="display: block; margin-bottom: 5px; font-weight: bold;">Сколько часов наиграно в BRM5 / Какой ранг:</label>
                    <input type="text" id="rank" placeholder="Например: 50 часов, Ранг 5" required style="width: 100%; padding: 10px; background-color: #0A0B0C; border: 1px solid #4C704C; color: #00FF41; box-sizing: border-box; font-family: inherit;">
                </div>

                <div style="margin-bottom: 20px;">
                    <label style="display: block; margin-bottom: 5px; font-weight: bold;">Why want to join:</label>
                    <textarea id="reason" rows="4" placeholder="Напишите пару предложений..." style="width: 100%; padding: 10px; background-color: #0A0B0C; border: 1px solid #4C704C; color: #00FF41; box-sizing: border-box; font-family: inherit; resize: none;"></textarea>
                </div>

                <button type="submit" style="background-color: #00FF41; color: #000; border: none; padding: 14px 25px; font-weight: bold; text-transform: uppercase; cursor: pointer; width: 100%; letter-spacing: 1px;">Отправить заявку в штаб</button>
            </form>
        </div>
    </div>

    <script>
        document.getElementById('clanForm').addEventListener('submit', function(e) {
            e.preventDefault();

            var webhookUrl = "https://discord.com";

            var roblox = document.getElementById('robloxNick').value;
            var discord = document.getElementById('discordId').value;
            var age = document.getElementById('age').value;
            var rank = document.getElementById('rank').value;
            var reason = document.getElementById('reason').value || "Не указано";

            var discordMessage = {
                content: "🔔 @everyone Поступила новая анкета на рядового!",
                embeds: [{
                    title: "⚔️ НОВАЯ ЗАЯВКА: АНКЕТА НА РЯДОВОГО ⚔️",
                    color: 524300, 
                    fields: [
                        { name: "👤 Ник в Roblox", value: roblox, inline: true },
                        { name: "📱 Discord тег", value: discord, inline: true },
                        { name: "🔞 Возраст", value: age, inline: true },
                        { name: "🎮 Стаж / Ранг в BRM5", value: rank, inline: false },
                        { name: "📝 Почему хочет к нам", value: reason, inline: false }
                    ],
                    timestamp: new Date()
                }]
            };

            var request = new XMLHttpRequest();
            request.open("POST", webhookUrl);
            request.setRequestHeader('Content-type', 'application/json');
            request.send(JSON.stringify(discordMessage));

            alert('Заявка успешно отправлена в штаб клана! Ожидайте ответа.');
            document.getElementById('clanForm').reset();
        });
    </script>
</body>
</html>
