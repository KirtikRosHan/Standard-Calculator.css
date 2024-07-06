## PROGRAM:

## calc.html
```c
<html lang="en">
  <head>
    
    <title>Calculator in HTML CSS & JavaScript</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    
    <div class="container">
      <h1 align="center">CALCULATOR</h1> 
      <h2 align="center"></h2>
      
      <input type="text" class="display" />

      <div class="buttons">
        <button class="operator" data-value="AC">AC</button>
        <button class="operator" data-value="DEL">DEL</button>
        <button class="operator" data-value="%">%</button>
        <button class="operator" data-value="/">/</button>

        <button data-value="7">7</button>
        <button data-value="8">8</button>
        <button data-value="9">9</button>
        <button class="operator" data-value="*">*</button>

        <button data-value="4">4</button>
        <button data-value="5">5</button>
        <button data-value="6">6</button>
        <button class="operator" data-value="-">-</button>

        <button data-value="1">1</button>
        <button data-value="2">2</button>
        <button data-value="3">3</button>
        <button class="operator" data-value="+">+</button>

        <button data-value="0">0</button>
        <button data-value="00">00</button>
        <button data-value=".">.</button>
        <button class="operator" data-value="=">=</button>
      </div>
    </div>

    <script src="script.js"></script>
  </body>
</html>

```
```c
/* Import Google font - Poppins */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}
body {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgb(13, 13, 13);
}

.container {
  position: relative;
  max-width: 500px;
  width: 100%;
  border-radius: 12px;
  padding: 10px 20px 20px;
  background: #6e6a6a;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.05);
}
.display {
  height: 80px;
  width: 100%;
  outline: none;
  border: none;
  text-align: right;
  margin-bottom: 10px;
  font-size: 25px;
  color: #000e1a;
  pointer-events: none;
}
.buttons {
  display: grid;
  grid-gap: 10px;
  grid-template-columns: repeat(4, 1fr);
}
.buttons button {
  padding: 10px;
  border-radius: 6px;
  border: none;
  font-size: 20px;
  cursor: pointer;
  background-color: #cb8a18;
}
.buttons button:active {
  transform: scale(0.99);
}
.operator {
  color: #d91111;
}

```
```c
const display = document.querySelector(".display");
const buttons = document.querySelectorAll("button");
const specialChars = ["%", "*", "/", "-", "+", "="];
let output = "";

const calculate = (btnValue) => {
  display.focus();
  if (btnValue === "=" && output !== "") {
    output = eval(output.replace("%", "/100"));
  } else if (btnValue === "AC") {
    output = "";
  } else if (btnValue === "DEL") {
    output = output.toString().slice(0, -1);
  } else {
    if (output === "" && specialChars.includes(btnValue)) return;
    output += btnValue;
  }
  display.value = output;
};

buttons.forEach((button) => {
  button.addEventListener("click", (e) => calculate(e.target.dataset.value));
});

```
## OUTPUT:
![alt text](<Screenshot (38)-1.png>)
![alt text](<Screenshot (39)-1.png>) 
