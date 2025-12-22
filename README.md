<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Chat Story</title>
  <style>
    body {
      margin: 0;
      background: #000;
      font-family: Arial, sans-serif;
      color: white;
    }

    #chat {
      padding: 15px;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .msg {
      max-width: 70%;
      padding: 10px 14px;
      border-radius: 14px;
      line-height: 1.4;
    }

    .left {
      align-self: flex-start;
      background: #2a2a2a;
    }

    .right {
      align-self: flex-end;
      background: #5a2cff;
    }

    #tap {
      position: fixed;
      bottom: 0;
      width: 100%;
      padding: 15px;
      text-align: center;
      background: #111;
      cursor: pointer;
    }
  </style>
</head>
<body>

<div id="chat"></div>

<div id="tap">Нажми, чтобы продолжить</div>

<script>
const story = [
  { from: "Эрик", side: "left", text: "Привет." },
  { from: "Элла", side: "right", text: "Привет." },
  { from: "Эрик", side: "left", text: "Ты здесь?" }
];

let index = 0;
const chat = document.getElementById("chat");

document.getElementById("tap").onclick = () => {
  if (index >= story.length) return;

  const msg = document.createElement("div");
  msg.className = "msg " + story[index].side;
  msg.textContent = story[index].from + ": " + story[index].text;
  chat.appendChild(msg);

  index++;
  window.scrollTo(0, document.body.scrollHeight);
};
</script>

</body>
</html>
