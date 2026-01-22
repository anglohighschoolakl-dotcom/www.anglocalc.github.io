<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Calculator</title>
<style>
    body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background: #f1f3f4;
        font-family: Arial, sans-serif;
    }

    .calculator {
        width: 320px;
        background: #fff;
        border-radius: 12px;
        box-shadow: 0 4px 10px rgba(0,0,0,0.15);
        padding: 15px;
    }

    .display {
        width: 100%;
        height: 60px;
        font-size: 28px;
        text-align: right;
        border: none;
        outline: none;
        margin-bottom: 10px;
        padding: 10px;
        background: #f1f3f4;
        border-radius: 8px;
    }

    .buttons {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 10px;
    }

    button {
        height: 55px;
        font-size: 20px;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        background: #e8eaed;
    }

    button.operator {
        background: #dadce0;
    }

    button.equal {
        background: #1a73e8;
        color: white;
        grid-column: span 2;
    }

    button.clear {
        background: #ea4335;
        color: white;
    }

    button:hover {
        opacity: 0.9;
    }
</style>
</head>
<body>

<div class="calculator">
    <input type="text" class="display" id="display" disabled>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="appendValue('%')">%</button>
        <button onclick="appendValue('/')">÷</button>
        <button class="operator" onclick="appendValue('*')">×</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button class="operator" onclick="appendValue('-')">−</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button class="operator" onclick="appendValue('+')">+</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button onclick="appendValue('.')">.</button>

        <button onclick="appendValue('0')">0</button>
        <button class="equal" onclick="calculate()">=</button>
    </div>
</div>

<script>
    const display = document.getElementById("display");

    function appendValue(value) {
        display.value += value;
    }

    function clearDisplay() {
        display.value = "";
    }

    function calculate() {
        try {
            display.value = eval(display.value);
        } catch {
            display.value = "Error";
        }
    }

    // Keyboard support
    document.addEventListener("keydown", (e) => {
        if ("0123456789+-*/.%".includes(e.key)) {
            appendValue(e.key);
        } else if (e.key === "Enter") {
            calculate();
        } else if (e.key === "Backspace") {
            display.value = display.value.slice(0, -1);
        } else if (e.key === "Escape") {
            clearDisplay();
        }
    });
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Calculator</title>
<style>
    body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background: #f1f3f4;
        font-family: Arial, sans-serif;
    }

    .calculator {
        width: 320px;
        background: #fff;
        border-radius: 12px;
        box-shadow: 0 4px 10px rgba(0,0,0,0.15);
        padding: 15px;
    }

    .display {
        width: 100%;
        height: 60px;
        font-size: 28px;
        text-align: right;
        border: none;
        outline: none;
        margin-bottom: 10px;
        padding: 10px;
        background: #f1f3f4;
        border-radius: 8px;
    }

    .buttons {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 10px;
    }

    button {
        height: 55px;
        font-size: 20px;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        background: #e8eaed;
    }

    button.operator {
        background: #dadce0;
    }

    button.equal {
        background: #1a73e8;
        color: white;
        grid-column: span 2;
    }

    button.clear {
        background: #ea4335;
        color: white;
    }

    button:hover {
        opacity: 0.9;
    }
</style>
</head>
<body>

<div class="calculator">
    <input type="text" class="display" id="display" disabled>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="appendValue('%')">%</button>
        <button onclick="appendValue('/')">÷</button>
        <button class="operator" onclick="appendValue('*')">×</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button class="operator" onclick="appendValue('-')">−</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button class="operator" onclick="appendValue('+')">+</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button onclick="appendValue('.')">.</button>

        <button onclick="appendValue('0')">0</button>
        <button class="equal" onclick="calculate()">=</button>
    </div>
</div>

<script>
    const display = document.getElementById("display");

    function appendValue(value) {
        display.value += value;
    }

    function clearDisplay() {
        display.value = "";
    }

    function calculate() {
        try {
            display.value = eval(display.value);
        } catch {
            display.value = "Error";
        }
    }

    // Keyboard support
    document.addEventListener("keydown", (e) => {
        if ("0123456789+-*/.%".includes(e.key)) {
            appendValue(e.key);
        } else if (e.key === "Enter") {
            calculate();
        } else if (e.key === "Backspace") {
            display.value = display.value.slice(0, -1);
        } else if (e.key === "Escape") {
            clearDisplay();
        }
    });
</script>

</body>
</html>
