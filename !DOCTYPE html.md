<!DOCTYPE html>  
<html lang="en">  
<head>  
  <meta charset="UTF-8">  
  <title>Kye 💖 Special Question</title>  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <style>  
    body {  
      background: linear-gradient(to bottom, #ffd6e8, #fff0f5);  
      font-family: "Comic Sans MS", cursive;  
      text-align: center;  
      overflow: hidden;  
      height: 100vh;  
      margin: 0;  
      transition: all 0.5s ease;  
    }  
  
    h1 {  
      margin-top: 50px;  
      color: #ff4d88;  
      font-size: 32px;  
      padding: 0 10px;  
    }  
  
    h2 {  
      color: #ff4d88;  
      font-size: 26px;  
      padding: 0 10px;  
    }  
  
    .container {  
      margin-top: 40px;  
      position: relative;  
      height: 250px;  
    }  
  
    button {  
      font-size: 24px;  
      padding: 20px 40px;  
      border-radius: 40px;  
      border: none;  
      cursor: pointer;  
      position: absolute;  
      transition: all 0.3s ease;  
      touch-action: manipulation;  
    }  
  
    #yes {  
      background-color: #ff4d88;  
      color: white;  
      left: 35%;  
      top: 120px;  
    }  
  
    #no {  
      background-color: #aaa;  
      color: white;  
      left: 55%;  
      top: 120px;  
    }  
  
    #next {  
      background-color: #ff4d88;  
      color: white;  
      padding: 20px 40px;  
      font-size: 24px;  
      border-radius: 40px;  
      border: none;  
      cursor: pointer;  
      display: none;  
      margin-top: 50px;  
    }  
  
    .heart, .flower, .confetti {  
      position: absolute;  
      font-size: 28px;  
      animation: floatUp 5s linear infinite;  
      pointer-events: none;  
    }  
  
    @keyframes floatUp {  
      0% { transform: translateY(0); opacity: 1; }  
      100% { transform: translateY(-800px); opacity: 0; }  
    }  
  
    .gif-container {  
      margin-top: 20px;  
    }  
  
    img {  
      max-width: 50%;  
      border-radius: 15px;  
    }  
  </style>  
</head>  
<body>  
  <h1 id="question-header">Kye… since December, I’ve really enjoyed talking to you 💖</h1>  
  <h2 id="sub-header">Will you be my girlfriend?</h2>  
  
  <div class="container" id="button-container">  
    <button id="yes">Yes</button>  
    <button id="no">No</button>  
  </div>  
  
  <button id="next">Next</button>  
  
  <div class="gif-container">  
    <img src="https://media.giphy.com/media/l41lFw057lAJQMwg0/giphy.gif" alt="hearts gif">  
  </div>  
  
  <script>  
    const yesBtn = document.getElementById('yes');  
    const noBtn = document.getElementById('no');  
    const nextBtn = document.getElementById('next');  
    const questionHeader = document.getElementById('question-header');  
    const subHeader = document.getElementById('sub-header');  
    const buttonContainer = document.getElementById('button-container');  
  
    const yesTexts = ["Yes!", "Absolutely!", "Of course!", "Please 💖", "Yaaas!"];  
  
    // Step 1: Ask to be girlfriend  
    yesBtn.addEventListener('click', () => {  
      questionHeader.innerText = "I will love you, cherish you forever 💖";  
      subHeader.innerText = "I can't wait to be your girlfriend!";  
      buttonContainer.style.display = "none";  
      nextBtn.style.display = "inline-block";  
    });  
  
    // No button runs away on touch/mouseover  
    function moveNoButton() {  
      const x = Math.random() * (window.innerWidth - noBtn.offsetWidth - 20);  
      const y = Math.random() * (window.innerHeight - noBtn.offsetHeight - 100);  
      noBtn.style.left = `${x}px`;  
      noBtn.style.top = `${y}px`;  
    }  
    noBtn.addEventListener('touchstart', moveNoButton);  
    noBtn.addEventListener('mouseover', moveNoButton);  
  
    // Yes button grows and changes text on tap/mouseover  
    function yesEffect() {  
      yesBtn.style.transform = `scale(${1 + Math.random() * 0.3})`;  
      yesBtn.innerText = yesTexts[Math.floor(Math.random() * yesTexts.length)];  
    }  
    yesBtn.addEventListener('mouseover', yesEffect);  
    yesBtn.addEventListener('touchstart', yesEffect);  
  
    // Step 2: Ask to be Valentine  
    nextBtn.addEventListener('click', () => {  
      questionHeader.innerText = "Will you be my Valentine? 💖";  
      subHeader.innerText = "";  
      nextBtn.style.display = "none";  
      buttonContainer.style.display = "block";  
      yesBtn.innerText = "Yes";  
      yesBtn.style.transform = "scale(1)";  
    });  
  
    // Step 3: Celebrate when she clicks Yes for Valentine  
    yesBtn.addEventListener('click', () => {  
      if (questionHeader.innerText.includes("Valentine")) {  
        questionHeader.innerText = "Yay!! 💖🌸 I’m so happy!!";  
        subHeader.innerText = "I can't wait to celebrate with you!";  
        buttonContainer.style.display = "none";  
  
        // explode hearts & flowers  
        for (let i = 0; i < 100; i++) {  
          const confetti = document.createElement('div');  
          confetti.classList.add('confetti');  
          confetti.innerText = ["💖","🌸","💐","🎉"][Math.floor(Math.random()*4)];  
          confetti.style.left = Math.random() * window.innerWidth + 'px';  
          confetti.style.top = Math.random() * window.innerHeight + 'px';  
          confetti.style.fontSize = 20 + Math.random() * 30 + 'px';  
          document.body.appendChild(confetti);  
          setTimeout(() => confetti.remove(), 5000 + Math.random()*3000);  
        }  
      }  
    });  
  
    // Floating hearts & flowers continuously  
    setInterval(() => {  
      const heart = document.createElement('div');  
      heart.classList.add('heart');  
      heart.innerText = Math.random() > 0.5 ? '💖' : '🌸';  
      heart.style.left = Math.random() * window.innerWidth + 'px';  
      heart.style.fontSize = 20 + Math.random() * 30 + 'px';  
      document.body.appendChild(heart);  
      setTimeout(() => heart.remove(), 5000);  
    }, 500);  
  
  </script>  
</body>  
</html>  
