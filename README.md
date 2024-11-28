# Calculator-built-for-beginner-Project

**HTML File**

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>calculator</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
</head>
<body>
    <div class="calculator">
        <input type="text" placeholder="0">
        <div>
            <button>Rad</button>
            <button>X!</button>
            <button>(</button>
            <button>)</button>
        
            <button>AC</button>
            <button>INV</button>
        <button>IN</button>
        <button>|reg</button>
            

    </div>

    <div>
        
        <button>SIN</button>
        <button>7</button>
        <button>8</button>
        <button>9</button>
        <button>/</button>
        <button>6</button>
        <button>5</button>
        <button>4</button>
    </div>
    <div>
        
        <button>3</button>
        <button>2</button>
        <button>1</button>
        <button>0</button>
        
        <button class="operator">+</button>
        <button class="operator">%</button>
        <button class="operator">-</button>
        <button class="operator">*</button>
        
    </div>
    <div><button class="equalbtn">=</button></div>
</body>

</html>

**CSS File**

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
</style>
*{

    margin: 0;
    padding: 0;
    box-sizing: border-box;
    .poppins-semibold-italic 
        font-family: "Poppins", serif;
        font-weight: 600;
        font-style: italic;
      
}

body{
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(40deg,#0a0a0a,#3a4452);
}

.calculator{
    border: 1px solid #717377;
    padding: 20px;
    margin: 40px;
    border-radius: 16px;
    background: transparent;
    box-shadow: 0px 3px 15px solid rgba(203, 25, 25));

}

input{
    width: 320px;
    border: none;
    padding: 4px;
    margin: 10px;
    background: transparent;
    box-shadow: 0px 3px 15px rgba(84,84,84,0.1);
    font-size: 40px;
    text-align: right;
cursor: pointer;

}

input::placeholder{
    color: white;
}

button{
    border: none;
    width: 60px;
    height: 60px;
    margin: 10px;
    border-radius: 50%;
    background: transparent;
    color: white;
    font-size: 20px;
    box-shadow: -8px -8px 15px #2a538d;
    cursor: pointer;
}

.equalbtn{
    background-color: rgb(225, 194, 14);
}

.operator{
    background-color: aquamarine;
}

****JAVA SCRIPT CODE

let input = document.getElementById('inputbox');
let buttons = document.querySelectorAll('button');
let string = "";
let arr = Array.from(buttons);

arr.forEach(button => {
  button.addEventListener('click', (e) => {
    if (e.target.innerHTML == '=') {
      try {
        string = eval(string); // Evaluate the input expression
        input.value = string;
      } catch {
        input.value = "Error"; // Handle invalid expressions
        string = "";
      }
    } else if (e.target.innerHTML == 'C') {
      string = ""; // Clear all input
      input.value = string;
    } else if (e.target.innerHTML == 'DEL') {
      string = string.substring(0, string.length - 1); // Remove last character
      input.value = string;
    } else {
      string += e.target.innerHTML; // Append the clicked button value
      input.value = string;
    }
  });
});




