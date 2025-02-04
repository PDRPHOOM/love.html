# love.html<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Love Letter</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: #fbe3c8;
            font-family: Arial, sans-serif;
            flex-direction: column;
        }
        .container {
            position: relative;
            width: 300px;
            height: 250px;
        }
        .envelope {
            position: absolute;
            width: 100%;
            height: 100%;
            background: #c69c6d;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            transition: transform 0.5s ease-in-out;
        }
        .flap {
            position: absolute;
            width: 100%;
            height: 50%;
            background: #b38b5d;
            top: 0;
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;
            transition: transform 0.5s ease-in-out;
            transform-origin: top;
        }
        .letter {
            position: absolute;
            width: 90%;
            height: 150px;
            background: white;
            top: 100px;
            border-radius: 5px;
            text-align: center;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transition: top 0.8s ease-in-out, opacity 0.8s ease-in-out;
            opacity: 0;
        }
        .heart {
            position: absolute;
            bottom: 5px;
            width: 30px;
            height: 30px;
            background: red;
            clip-path: polygon(50% 0%, 100% 30%, 80% 100%, 50% 80%, 20% 100%, 0% 30%);
        }
        .open .flap {
            transform: rotateX(180deg);
        }
        .open .letter {
            top: -30px;
            opacity: 1;
        }
        .btn {
            margin-top: 20px;
            padding: 10px 20px;
            background: #d35400;
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            font-size: 16px;
            transition: background 0.3s;
        }
        .btn:hover {
            background: #e67e22;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="flap"></div>
        <div class="envelope">
            <div class="letter">
                <p><strong>ສຸກສັນວັນວາເລນທາຍ 💌</strong></p>
                <p>ບໍ່ຮູ້ສິໃຫ້ຫຍັງ ແຕ່ຕັ້ງໃຈເຮັດອັນນີ້ໃຫ້ສຸດໆ.</p>
                <p>ຮັກສຸດໆເລີຍ. 💖</p>
            </div>
            <div class="heart"></div>
        </div>
    </div>
    
    <button class="btn" onclick="toggleLetter()">ເປີດເບິ່ງ
    <script>
        function toggleLetter() {
            let envelope = document.querySelector('.envelope');
            let flap = document.querySelector('.flap');
            let letter = document.querySelector('.letter');
            let button = document.querySelector('.btn');

            if (envelope.classList.contains('open')) {
                envelope.classList.remove('open');
                button.textContent = "Open Letter";
            } else {
                envelope.classList.add('open');
                button.textContent = "Close Letter";
            }
        }
    </script>

</body>
</html>
