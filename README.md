<!DOCTYPE html>
<html>
<head>
  <title>Joguinho da Júlia 💕</title>
  <style>
    body {
      text-align: center;
      font-family: Arial;
      background: linear-gradient(to bottom, #ffe6f2, #fff5fa);
      padding: 40px;
      overflow: hidden;
    }

    h1 { color: #ff3399; }

    button {
      padding: 10px 20px;
      margin: 10px;
      font-size: 16px;
      border-radius: 20px;
      border: none;
      background-color: #ff66b3;
      color: white;
      cursor: pointer;
    }

    #final {
      display: none;
      margin-top: 30px;
      font-size: 20px;
      color: #cc0066;
    }

    .heart {
      position: fixed;
      top: -10px;
      font-size: 20px;
      animation: fall 5s linear infinite;
    }

    @keyframes fall {
      to { transform: translateY(100vh); }
    }
  </style>
</head>
<body>

<h1>Missão: Descobrir o Amor 💘</h1>

<div id="game">
  <p>Júlia, você está preparada? 😏</p>
  <button onclick="pergunta1()">Tô sim 😌</button>
</div>

<div id="final">
  <p>
    EU AMO VOCÊ ❤️<br><br>
    Eu queria dizer isso sempre no seu ouvidinho… 🥹<br><br>
    O quanto você me faz bem,<br>
    o quanto você é o meu amor,<br>
    e o quanto eu estou com MUITA saudade de você. 💕<br><br>
    Ass: Sua programadora apaixonada 😎💻❤️
  </p>
</div>

<script>
function pergunta1() {
  document.getElementById("game").innerHTML =
  "<p>O que você é pra mim?</p>" +
  "<button onclick='errado()'>Um pastel de feira 🥟</button>" +
  "<button onclick='certo1()'>Meu amor ❤️</button>";
}

function certo1() {
  document.getElementById("game").innerHTML =
  "<p>O que você me faz sentir?</p>" +
  "<button onclick='errado()'>Fome 😋</button>" +
  "<button onclick='certo2()'>Paz e felicidade ✨</button>";
}

function certo2() {
  document.getElementById("game").innerHTML =
  "<p>E o que eu estou sentindo agora?</p>" +
  "<button onclick='errado()'>Sono 😴</button>" +
  "<button onclick='mostrarFinal()'>Muita saudade 💕</button>";
}

function errado() {
  alert("ERROU 😝 tenta de novo, linda!");
}

function mostrarFinal() {
  document.getElementById("game").style.display = "none";
  document.getElementById("final").style.display = "block";
  chuva();
}

function chuva() {
  setInterval(function() {
    var heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = (Math.random() * 20 + 10) + "px";
    document.body.appendChild(heart);

    setTimeout(function() {
      heart.remove();
    }, 5000);
  }, 300);
}
</script>

</body>
</html>
