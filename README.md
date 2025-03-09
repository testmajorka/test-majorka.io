# test-majorka.io
<!DOCTYPE html> 
<html lang="ru"> 
<head> 
    <meta charset="UTF-8"> 
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> 
    <title>Изображение с Imgur</title> 
</head> 
<body> 
    <!-- Тег img используется для отображения изображения --> 
    <img src="https://i.imgur.com/XDnv6yt.jpg" alt="Описание изображения" width="80" height="20"> 
    <!-- alt предоставляет текстовое описание изображения для доступности --> 
    <html lang="ru">   
<head>   
    <meta charset="UTF-8">   
    <meta name="viewport" content="width=device-width, initial-scale=1.0">   
    <link rel="stylesheet" href="styles.css">   
    <title>Мой Сайт</title>   
</head>   
<body>   
    <header>   
        <h1 style="font-family: 'Arial', sans-serif; color: #000000; text-align: center; text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);">Добро пожаловать на сайт покупки виртуальных товаров!</h1>  
    </header>   
    <main>   
        <h2>Зачем часами копать шахту, если можно за минуту купить вирты Матрешка RP на нашей торговой площадке. Позволь себе гелик и огромную виллу — живи шикарной жизнью. На VirtShop работают проверенные продавцы и все сделки безопасны</h2>   
<p>===================================================================================</p>  
   
    </main>   
    <footer>   
        <h2 style="font-family: 'Arial', sans-serif; color: #000000; text-align: center; text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);">Цены на покупку виртуальных валют на проекте</h2>   
    </footer>   
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>Кнопки</title>  
  <!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Кнопки</title>
    <style>
        .button {
            display: inline-block;
            border: none;
            border-radius: 22px;
            color: white;
            padding: 15px 30px;
            font-size: 15px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            text-decoration: none;
            transition: transform 0.3s, box-shadow 0.3s;
            margin: 5px;
        }
        .button1 {
            background: linear-gradient(45deg, #4d003b, #ff00ff);
        }
        .button2 {
            background: linear-gradient(45deg, #ff0000, #000000);
        }
        .button3 {
            background: linear-gradient(45deg, #FFFF00, #F4A460);
        }
        .button4 {
            background: linear-gradient(45deg, #000000, #696969);
        }
        .button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 25px rgba(0, 0, 0, 0.3);
            filter: brightness(1.1);
        }
        #resultContainer {
            display: none; /* Скрываем контейнер с результатами по умолчанию */
        }
    </style>
</head>
<body>

<h1>Поиск</h1>
<input type="text" id="searchInput" placeholder="Введите название игры..." onkeyup="filterButtons()">

<div id="buttonsContainer">
    <a href="https://funpay.com/chips/187/" class="button button1" value="Матрешка">Матрешка</a>
    <a href="https://funpay.com/chips/186/" class="button button2" value="Black Russia">Black Russia</a>
    <a href="https://funpay.com/chips/185/" class="button button3" value="Radmir">Radmir</a>
    <a href="https://funpay.com/chips/51/" class="button button4" value="другое">другое</a>
</div>

<div id="resultContainer" style="margin-top: 20px;">
    <h2>Результаты поиска:</h2>
    <div id="filteredButtons"></div>
</div>

<script>
    function translitToCyrillic(text) {
        const translitMap = {
            'a': 'а', 'b': 'б', 'v': 'в', 'g': 'г', 'd': 'д', 'e': 'е', 'yo': 'ё',
            'zh': 'ж', 'z': 'з', 'i': 'и', 'j': 'й', 'k': 'к', 'l': 'л', 'm': 'м',
            'n': 'н', 'o': 'о', 'p': 'п', 'r': 'р', 's': 'с', 't': 'т', 'u': 'у',
            'f': 'ф', 'h': 'х', 'ts': 'ц', 'ch': 'ч', 'sh': 'ш', 'sch': 'щ',
            'y': 'ы', 'e': 'э', 'yu': 'ю', 'ya': 'я',
            'bl': 'бл', 'ek': 'ек', 'ra':'ра', 'sha': 'ша',
            'm': 'м', 't': 'т', 'p': 'п'
        };

        return text.toLowerCase().split(' ').map(word => {
            return word.split('').map(letter => translitMap[letter] || letter).join('');
        }).join(' ');
    }

    function filterButtons() {
        const input = document.getElementById('searchInput').value.toLowerCase();
        const buttons = document.querySelectorAll('#buttonsContainer a');
        const filteredButtonsContainer = document.getElementById('filteredButtons');
        const resultContainer = document.getElementById('resultContainer');

        filteredButtonsContainer.innerHTML = '';
        let hasResults = false;

        // Проверяем все кнопки
        buttons.forEach(button => {
            const buttonText = button.textContent.toLowerCase();
            const translitText = translitToCyrillic(buttonText);

            if ((buttonText.includes(input) || translitText.includes(input)) && input.trim() !== '') {
                const clonedButton = button.cloneNode(true);
                filteredButtonsContainer.appendChild(clonedButton);
                hasResults = true;
            }
        });

        if (hasResults) {
            resultContainer.style.display = 'block'; // Показываем контейнер с результатами
        } else {
            resultContainer.style.display = 'none'; // Скрываем контейнер с результатами
        }

        // Если поле ввода пустое, показываем все кнопки
        if (input.trim() === '') {
            buttons.forEach(button => {
                button.style.display = 'inline-block'; // Показываем все кнопки
  });
            resultContainer.style.display = 'none'; // Скрываем контейнер с результатами
        } else {
            buttons.forEach(button => {
                const buttonText = button.textContent.toLowerCase();
                const translitText = translitToCyrillic(buttonText);
                button.style.display = (buttonText.includes(input) || translitText.includes(input)) ? 'inline-block' : 'none'; // Показываем или скрываем кнопку
            });
        }
    }
</script>


    
</body>
</html>
