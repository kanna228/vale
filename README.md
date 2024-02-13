<html>
<head>
    <title>Valentinka for my love</title>
    <style>
        body {
            background-image: url("https://i.pinimg.com/564x/9e/48/28/9e48285a5c5d2580304c43e2a3414f49.jpg");

        }
        h1 {
            color: deeppink;
            text-align: center;
            font-family: serif;
            font-size: 3em;
        }
        .centered {
            display: flex;
            justify-content: center;
            align-items: center;
            padding-top: 7%;
        }
        .centered2 {
            display: flex;
            justify-content: center;
            align-items: center;
        }
        img {
            width: 70%;
            height: auto;
            max-width: 350px;
            max-height: 80vh; 
        }
        @media only screen and (max-width: 768px) {
            h1 {
                font-size: 10ex;
            }
            img {
                width: 80vh;
                height: 80vh;
            }
        }
        .button {
            display: inline-block;
            padding: 15px 30px;
            font-size: 16px;
            cursor: pointer;
            border: none;
            border-radius: 10px;
            margin: 10px;
            transition: background-color 0.3s;
            text-decoration: none;
            font-size: 3em;

        }
        .green {
            background-color: rgb(34, 255, 34);
            color: whitesmoke;
            font-family: serif;
        }
        .red {
            background-color: rgb(255, 71, 71);
            color: whitesmoke;
            font-family: serif;

        }
    </style>
</head>
<body>
    <div class="centered">
    <img src="https://i.pinimg.com/originals/eb/8d/c1/eb8dc1b0d517739a7adba71983796aa7.gif">
    </div>
    <h1>Will you be my Valentine?</h1>
    <div class="centered2">
    <button class="button green " onclick="goToNextPage()">Yes!!</button>
    <button id="redButton" class="button red" onclick="moveRed()">No...</button>
    </div>
    <div id="displayText" style="display: none; text-align: center;">
        <p style="color: deeppink; font-size: 2em; font-family: serif;">You don't have a choice dear</p>
    </div>
    <script>

        function moveRed() {
            var redButton = document.getElementById('redButton');
            var maxX = window.innerWidth - redButton.offsetWidth;
            var maxY = window.innerHeight - redButton.offsetHeight;
            var newX = Math.floor(Math.random() * maxX);
            var newY = Math.floor(Math.random() * maxY);
            redButton.style.position = 'absolute';
            redButton.style.left = newX + 'px';
            redButton.style.top = newY + 'px';
            var greenButton = document.querySelector('.green');
            var currentSize = window.getComputedStyle(greenButton).fontSize;
            var newSize = parseInt(currentSize) + 5;
            greenButton.style.fontSize = newSize + 'px';
            var interval = setInterval(function() {
                if (parseInt(greenButton.style.fontSize) >= newSize) {
                    clearInterval(interval);
                } else {
                    var currentSize = parseInt(greenButton.style.fontSize) + 1;
                    greenButton.style.fontSize = currentSize + 'px';
                }
            }, 20);

            var displayText = document.getElementById('displayText');
            displayText.style.display = 'block';
        }
        function goToNextPage() {
            window.location.href = "Valentinka_page2.html";
        }
    </script>
</body>
</html>
