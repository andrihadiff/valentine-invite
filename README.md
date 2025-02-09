<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine? 💖</title>
    <style>
        body {
            background-color: pink;
            text-align: center;
            font-family: Arial, sans-serif;
        }
        h1 {
            color: red;
            font-size: 40px;
            margin-top: 30px;
        }
        p {
            font-size: 24px;
        }
        .cinnamoroll {
            width: 200px;
            transition: transform 0.5s ease-in-out;
        }
        .cinnamoroll:hover {
            transform: scale(1.1);
        }
        .btn {
            padding: 15px 30px;
            font-size: 20px;
            background-color: white;
            border: 2px solid red;
            border-radius: 10px;
            cursor: pointer;
            margin: 20px;
            transition: 0.3s;
            position: absolute;
        }
        .btn:hover {
            background-color: red;
            color: white;
        }
        #yes-btn {
            left: 45%;
            top: 60%;
        }
        #no-btn {
            left: 55%;
            top: 60%;
        }
        #response {
            display: none;
            font-size: 28px;
            color: red;
            margin-top: 20px;
        }
        #hearts {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
        }
    </style>
</head>
<body>

    <h1>Please be my valentine. 💕</h1>
    
    <!-- Cinnamoroll Image -->
    <img src="cinnamoroll1.png" alt="Cinnamoroll" class="cinnamoroll">

    <p>Click below to answer:</p>
    
    <!-- Buttons -->
    <button class="btn" id="yes-btn" onclick="showResponse(true)">Yes 💖</button>
    <button class="btn" id="no-btn" onmouseover="moveButton()">No 😢</button>

    <!-- Response Message -->
    <div id="response"></div>

    <!-- Hearts Animation -->
    <div id="hearts"></div>

    <script>
        function showResponse(isYes) {
            let response = document.getElementById("response");
            let hearts = document.getElementById("hearts");
            
            if (isYes) {
                response.innerHTML = "I love you, my favorite nerd.";
                response.style.color = "red";
                startHearts();
            }

            response.style.display = "block";
        }

        function moveButton() {
            let noBtn = document.getElementById("no-btn");
            let newX = Math.random() * (window.innerWidth - 100); // Adjusts to screen size
            let newY = Math.random() * (window.innerHeight - 100);
            
            noBtn.style.left = `${newX}px`;
            noBtn.style.top = `${newY}px`;
        }

        function startHearts() {
            let heartsContainer = document.getElementById("hearts");
            for (let i = 0; i < 20; i++) {
                let heart = document.createElement("div");
                heart.innerHTML = "❤️";
                heart.style.position = "absolute";
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.top = Math.random() * 100 + "vh";
                heart.style.fontSize = Math.random() * 30 + 10 + "px";
                heart.style.animation = "floatUp 3s linear infinite";
                heartsContainer.appendChild(heart);
            }
        }
    </script>

</body>
</html>
