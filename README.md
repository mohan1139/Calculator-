# Calculator-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f0f0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .calculator {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
    }

    .display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: right;
      margin-bottom: 10px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }

    .buttons button {
      padding: 15px;
      font-size: 18px;
      cursor: pointer;
      border: none;
      border-radius: 5px;
      background: #e0e0e0;
      transition: background 0.2s;
    }

    .buttons button:hover {
      background: #d0d0d0;
    }

    .buttons .equal {
      background: #4CAF50;
      color: white;
    }

    .buttons .equal:hover {
      background: #45a049;
    }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" class="display" id="display" disabled>
  <div class="buttons">
    <button onclick="press('7')">7</button>
    <button onclick="press('8')">8</button>
    <button onclick="press('9')">9</button>
    <button onclick="press('/')">/</button>

    <button onclick="press('4')">4</button>
    <button onclick="press('5')">5</button>
    <button onclick="press('6')">6</button>
    <button onclick="press('*')">*</button>

    <button onclick="press('1')">1</button>
    <button onclick="press('2')">2</button>
    <button onclick="press('3')">3</button>
    <button onclick="press('-')">-</button>

    <button onclick="press('0')">0</button>
    <button onclick="press('.')">.</button>
    <button onclick="calculate()" class="equal">=</button>
    <button onclick="press('+')">+</button>

    <button onclick="clearDisplay()" style="grid-column: span 4;">C</button>
  </div>
</div>

<script>
  function press(value) {
    document.getElementById('display').value += value;
  }

  function calculate() {
    try {
      const result = eval(document.getElementById('display').value);
      document.getElementById('display').value = result;
    } catch {
      document.getElementById('display').value = 'Error';
    }
  }

  function clearDisplay() {
    document.getElementById('display').value = '';
  }
</script>

</body>
</html>
