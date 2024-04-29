### Ex.08 Design of a Standard Calculator
## Date:29/04/2024

## AIM:
To design a web application for a standard calculator with minimum five operations.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for creating attractive colors.

### Step 4:
Write JavaScript program for implementing five different operations.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

```

calc.html

<html lang="en">

<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>CALCULATOR</title>
   
        

      

   <script>
      function display(val) {
         document.getElementById('result').value += val;
      }
      function SolveCalculation() {
         var x = document.getElementById('result').value;
         var y = eval(x);
         document.getElementById('result').value = y;

      }
      function ClearFuntion() {
         document.getElementById('result').value = ''
      }
      function deleteFuntion() {
         var temp = ''
         temp = document.getElementById('result').value;
         var len = temp.length;
         temp = temp.substring(0, len - 1)
         document.getElementById('result').value = temp;
      }
      function squareRoot(){
         var x = document.getElementById('result').value ;
         var result = Math.pow(x,0.5)
         document.getElementById('result').value=result
      }

   </script>
   <style>
      .App-container {
         padding: 40px;
         margin-top: 2%;
         line-height: 40px;
         border: none;
         border-radius: 5px;
         box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.6), 0 6px 20px 0 rgba(0, 0, 0, 0.39);
         margin-left: 33%;
         margin-right:33%;
         text-align: center;
         background-color: cyan;
      }
      #h1{
         text-align: center;
      }
      #numberButton,
      #operatorButton,
      #clearButton,
      #deleteButton {
         padding: 20px;
         margin-top: 8px;
         margin-left: 10px;
         border: 5px;
         cursor: pointer;
         border-radius: 5px;

      }
      #EqualButton {
         border-radius: 5px;
         height: 57px;
         border: 5px;
         padding-left: 10px;
         background-color: rgb(155, 197, 61); 
         font-size: 20px;
         font-weight: 500;

      }
      #result {
         border-radius: 5px;
         height: 55px;
         border: 5px;
         padding-left: 15px;
         color: purple;
         font-size: 28px;
         font-weight: 500;


      }

      #operatorButton {
         background-color: rgb(245, 165, 114);
      }

      #deleteButton {
         background-color: rgb(255, 108, 92);
      }

      #clearButton {
         background-color: rgb(155, 81, 81);
      }

      .lastdiv {
         margin-left: 3px;
      }

      @media(max-width:580px) {
         .App-container {
            padding: 20px 0px;
            margin: 50% 6%;

         }
      }
   </style>
</head>



<body>
    <h2 align="center">Madhuvathani(212223040107) STANDARD CALCULATOR</h2>
    
   <div class="App-container">

      <input type="text" id="result" placeholder="Enter Value..." readonly="" />
      <input type="button" id="EqualButton" value="Ans" onclick="SolveCalculation()" />
      <div>
         <input type="button" id="numberButton" value="7" onclick="display('7')" />
         <input type="button" id="numberButton" value="8" onclick="display('8')" />
         <input type="button" id="numberButton" value="9" onclick="display('9')" />
         <input type="button" id="operatorButton" value="/" onclick="display('/')" />
      </div>
      <div>
         <input type="button" id="numberButton" value="4" onclick="display('4')" />
         <input type="button" id="numberButton" value="5" onclick="display('5')" />
         <input type="button" id="numberButton" value="6" onclick="display('6')" />
         <input type="button" id="operatorButton" value="*" onclick="display('')" />
      </div>
      <div>
         <input type="button" id="numberButton" value="1" onclick="display('1')" />
         <input type="button" id="numberButton" value="2" onclick="display('2')" />
         <input type="button" id="numberButton" value="3" onclick="display('3')" />
         <input type="button" id="operatorButton" value="-" onclick="display('-')" />
      </div>
      <div className='lastdiv'>
         <input type="button" id="numberButton" value="0" onclick="display('0')" />
         <input type="button" id="numberButton" value="." onclick="display('.')" />
        <input type="button" id="operatorButton" value="√" onclick="squareRoot()" /> 
	     <input type="button" id="operatorButton" value="+" onclick="display('+')" />
      </div>
      <div>
         <input type="button" id='deleteButton' value="Del" onclick="deleteFuntion()" />
         <input type="button" id="clearButton" onclick="ClearFuntion()" value="C" />
         <input type="button" id="operatorButton" value="=" onclick="display('=')" />

	
      </div>
   </div>
</body>
</html>


index.js
index.js
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


style.css

style.css
body{
    width:95%;
    height:90vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(90deg, #000000 0,#000000 58%);
    background-attachment: fixed;
    background-repeat: no-repeat;
    background-size: cover;
  }
  h3{
    color: #fff;
  }
  
  .card-title {
    font-size: 22px;
  }
  
  p, a {
    font-size: 1rem;
  }
  
  a {
    color: #4d4ae8;
    text-decoration: none;
  }
  .shape {
    position: absolute;
    width: 150px;
    top: .5rem;
    left: .5rem;
  }
  .calculator{
    background: #3a4452;
    padding: 20px;
    border-radius: 10px;
    width: 400px;
    height: auto;
      backdrop-filter: blur(50%);
    background-color: rgba(255, 255, 255, 0.2);
    border-radius: 10px;
    box-shadow: 0 15px 30px rgb(0, 0, 0);
    backdrop-filter: blur(4px); 
    -webkit-backdrop-filter: blur(4px); 
    padding: 20px;
  }
  .calculator form input{
    border: 0;
    outline: 0;
    width: 60;
    height: 60px;
    border-radius: 10px;
    box-shadow: -8px -8px 15px rgb(0, 0, 0),5px 5px 15px rgb(0, 0, 0);
    background: transparent;
    font-size: 20px;
    color: #00ff95;
    cursor: pointer;
    margin: 10px;
  }
  h3{
    color: crimson;
  }
  form .display{
    display: flex;
    justify-content: flex-end;
    margin: 20px 0;
  }
  form .display input{
    text-align: right;
    flex: 1;
    font-size: 45px;
    box-shadow: none;
  }
  form input.equal{
    width: 145px;
  }
  form input.operator{
    color:#00ff95;
  }


```

## OUTPUT:


![Screenshot 2024-04-29 213410](https://github.com/MADHUVATHANI/Calc/assets/149986415/8d3fa9e6-fb44-48cf-ba5a-3d1d0f7acc68)
![Screenshot 2024-04-29 213425](https://github.com/MADHUVATHANI/Calc/assets/149986415/166a1eca-b473-492b-b341-b77b30d89ba5)

## RESULT:
The program for designing a standard calculator using HTML and CSS is executed successfully.
