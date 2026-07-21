# ZOMBIE-SURVIVAL
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>좀비 게임</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      text-align: center;
      font-family: sans-serif;
      background: #111;
      color: white;
    }
    button {
      padding: 10px 20px;
      font-size: 18px;
      margin: 10px;
    }
  </style>
</head>
<body>

<h1>🧟 좀비 생존 게임</h1>
<p id="status">게임 시작 버튼을 누르세요</p>

<button onclick="startGame()">게임 시작</button>
<button onclick="attack()">공격</button>

<script>
let zombieHP;
let playerHP;

function startGame() {
  zombieHP = 10;
  playerHP = 10;
  document.getElementById("status").innerText =
    "좀비 등장! HP: " + zombieHP;
}

function attack() {
  if (zombieHP <= 0) {
    document.getElementById("status").innerText = "이미 처치됨!";
    return;
  }

  let damage = Math.floor(Math.random() * 5) + 1;
  zombieHP -= damage;

  if (zombieHP <= 0) {
    document.getElementById("status").innerText = "🧟 처치 성공!";
  } else {
    document.getElementById("status").innerText =
      "공격! -" + damage + " / 좀비 HP: " + zombieHP;
  }
}
</script>

</body>
</html>
