### 🛠 &nbsp;My Stack
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/css-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white)
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
<br>
![Laravel](https://img.shields.io/badge/laravel-%23FF2D20.svg?style=for-the-badge&logo=laravel&logoColor=white)
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![Next JS](https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white)
![Bootstrap](https://img.shields.io/badge/bootstrap-%23563D7C.svg?style=for-the-badge&logo=bootstrap&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)

### ⚙️ &nbsp;GitHub Analytics

<p align="start">
<a href="https://github.com/herdyy69">
  <img height="180em" src="https://github-readme-stats-eight-theta.vercel.app/api?username=herdyy69&show_icons=true&theme=algolia&include_all_commits=true&count_private=true"/>
  <img height="180em" src="https://github-readme-stats-eight-theta.vercel.app/api/top-langs/?username=herdyy69&layout=compact&langs_count=8&theme=algolia"/>
</a>
</p>

<!DOCTYPE html>
<html>
  <head>
    <title>Tic Tac Toe</title>
    <style>
      table {
        border-collapse: collapse;
        margin: auto;
      }
      td {
        width: 100px;
        height: 100px;
        border: 1px solid black;
        text-align: center;
        vertical-align: middle;
        font-size: 48px;
        font-weight: bold;
        cursor: pointer;
      }
      td:hover {
        background-color: #f0f0f0;
      }
    </style>
  </head>
  <body>
    <h1>Tic Tac Toe</h1>
    <table>
      <tr>
        <td id="0"></td>
        <td id="1"></td>
        <td id="2"></td>
      </tr>
      <tr>
        <td id="3"></td>
        <td id="4"></td>
        <td id="5"></td>
      </tr>
      <tr>
        <td id="6"></td>
        <td id="7"></td>
        <td id="8"></td>
      </tr>
    </table>
    <script>
      var currentPlayer = "X";
      var board = ["", "", "", "", "", "", "", "", ""];

      function handleClick(event) {
        var cell = event.target;
        var id = parseInt(cell.id);
        if (board[id] === "") {
          board[id] = currentPlayer;
          cell.innerText = currentPlayer;
          checkWin();
          togglePlayer();
        }
      }

      function togglePlayer() {
        currentPlayer = currentPlayer === "X" ? "O" : "X";
      }

      function checkWin() {
        var winningCombinations = [
          [0, 1, 2],
          [3, 4, 5],
          [6, 7, 8],
          [0, 3, 6],
          [1, 4, 7],
          [2, 5, 8],
          [0, 4, 8],
          [2, 4, 6]
        ];
        for (var i = 0; i < winningCombinations.length; i++) {
          var [a, b, c] = winningCombinations[i];
          if (board[a] !== "" && board[a] === board[b] && board[b] === board[c]) {
            alert("Player " + currentPlayer + " wins!");
            resetBoard();
            return;
          }
        }
        if (!board.includes("")) {
          alert("It's a tie!");
          resetBoard();
        }
      }

      function resetBoard() {
        board = ["", "", "", "", "", "", "", "", ""];
        var cells = document.getElementsByTagName("td");
        for (var i = 0; i < cells.length; i++) {
          cells[i].innerText = "";
        }
      }

      var cells = document.getElementsByTagName("td");
      for (var i = 0; i < cells.length; i++) {
        cells[i].addEventListener("click", handleClick);
      }
    </script>
  </body>
</html>

