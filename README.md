<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Libro Especial</title>
    <style>
        body {
            background-color: pink;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
        }
        .book-container {
            width: 300px;
            height: 400px;
            position: relative;
            perspective: 1000px;
        }
        .book {
            width: 100%;
            height: 100%;
            position: relative;
            transform-style: preserve-3d;
            transition: transform 0.7s;
        }
        .page {
            position: absolute;
            width: 100%;
            height: 100%;
            background: white;
            border-radius: 10px;
            box-shadow: 2px 2px 10px gray;
            text-align: center;
            padding: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            backface-visibility: hidden;
        }
        .page img {
            width: 100%;
            height: auto;
            position: absolute;
            z-index: -1;
        }
        .page1 { background: url('https://i.imgur.com/O5Zs8Fl.png') no-repeat center/cover; }
        .page2 { background: url('https://i.imgur.com/5a9X9Jr.png') no-repeat center/cover; transform: rotateY(180deg); }
        .page3 { background: url('https://i.imgur.com/dq6mU9s.png') no-repeat center/cover; transform: rotateY(360deg); }
        .page4 { background: url('https://i.imgur.com/A9Zo9Ty.png') no-repeat center/cover; transform: rotateY(540deg); }
        .page5 { background: url('https://i.imgur.com/79rQzPE.png') no-repeat center/cover; transform: rotateY(720deg); }
    </style>
</head>
<body>
    <div class="book-container" onclick="nextPage()">
        <div class="book" id="book">
            <div class="page page1">🐶 Página 1: Había una vez...</div>
            <div class="page page2">🐱 Página 2: Un lindo gatito...</div>
            <div class="page page3">🐰 Página 3: Que encontró amor...</div>
            <div class="page page4">🐻 Página 4: Y se llenó de alegría...</div>
            <div class="page page5">❤️ Página 5: ¡Feliz San Valentín!</div>
        </div>
    </div>

    <script>
        let currentPage = 0;
        function nextPage() {
            currentPage = (currentPage + 1) % 5;
            document.getElementById("book").style.transform = `rotateY(${currentPage * 180}deg)`;
        }
    </script>
</body>
</html>
