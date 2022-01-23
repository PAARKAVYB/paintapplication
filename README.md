
# Web Page for Paint Application

## AIM:

To design a static website for Paint Application using HTML5 canvas.

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML,CSS and canvas.

### Step 3:

Write javascript to capture move events.

### Step 4:

Perform the drawing operation based on the user input.

### Step 5:

Validate the layout in various browsers.

### Step 6:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :
```
<!DOCTYPE html>
<html>
  <head>
    <title>
      CANVAS
    </title>
    <link rel="stylesheet" href="./css/layout.css" />
    <link rel="icon" href="./img/logo.png" type="image/x-icon" />
  </head>
<body id="content">
    <h1>DRAWING APPLICATION</h1>
    <div id="container">
<canvas id="myCanvas" width="790" height="790" onclick="showCoords(event)"></canvas></div>
<center>
<button onclick="shape=1" id="keys" >Solid Circle </button>
<button onclick="shape=2" id="keys">Circle</button>
<button onclick="shape=3" id="keys">Solid Square</button>
<button onclick="shape=4" id="keys">Square</button>
<button onclick="shape=5" id="keys">Solid Triangle</button>
<button onclick="shape=6" id="keys">Triangle</button>
<br>
<button onclick="size()" id="keys" >Change size</button></center>
<center>
    <button onclick="using_color(this)" id="colour" style="background: white;"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(255, 72, 72);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(255, 115, 1);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(252, 255, 60);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(94, 255, 45);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(7, 184, 1);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(49, 231,252);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(46, 112, 255);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(213, 76, 255);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(153, 0, 255);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(54, 0, 124);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(0, 0, 0);"></button>
    </center>
<script>
const canvas = document.getElementById("myCanvas");
const ctx = canvas.getContext("2d");
ctx.fillStyle = "#FF0000";
canvas.height = canvas.width;
ctx.transform(1, 0, 0, -1, 0, canvas.height);
let xMax = canvas.height;
let yMax = canvas.width;
let csize= 20;
let sqsize= 50;
let tsize=30;
let words="black";
function size()
{   
if (shape==1 ||shape==2){
    let c= prompt("Please enter size of circle", "Enter you are value");
    csize=c;
} 
if (shape==3 ||shape==4){
    let s = prompt("Please enter size of square", "Enter you are value");
    sqsize=s;
}
if (shape==5 || shape==6){
    let t= prompt("Please enter size of square","Enter you are value");
    tsize=t;
}
}
function using_color(element){
    words=element.style.background;
}
    function showCoords(event)
    {
    var x = event.clientX-640;
    var y = 1135-event.clientY;
    var coords = "X coords: " + x + ", Y coords: " + y;
    document.getElementById("demo").innerHTML = coords;
    
        if (shape==1){
            ctx.beginPath();
            ctx.arc(x, y, csize, 0, 2 * Math.PI);
            ctx.fillStyle=words;
            ctx.fill();
        }
        if (shape==2){
            ctx.beginPath();
            ctx.arc(x, y, csize, 0, 2 * Math.PI);
            ctx.strokeStyle=words;
            ctx.stroke();
        }
        if (shape==3){
            ctx.beginPath();
            ctx.rect(x-(sqsize/2),y-(sqsize/2), sqsize,sqsize);
            ctx.fillStyle=words;
            ctx.fill();
        }
        if (shape==4){
            ctx.beginPath();
            ctx.rect(x-(sqsize/2),y-(sqsize/2), sqsize,sqsize);
            ctx.strokeStyle=words;
            ctx.stroke();
        }
        if (shape==6){
            ctx.beginPath();
            ctx.moveTo(x, y);
            ctx.lineTo(x-(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x+(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x,y)
            ctx.strokeStyle=words
            ctx.stroke();
        }
        if (shape==5){
            ctx.beginPath();
            ctx.moveTo(x, y);
            ctx.lineTo(x-(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x+(tsize/2),y-(tsize*0.86602));
            ctx.fillStyle=words
            ctx.fill();
        }
    }
</script>
<center><p id="demo" style="color: rgb(202, 0, 0);"></p></center>

<p style="color: rgb(2, 0, 2); font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, 
Cantarell,'Open Sans', 'Helvetica Neue', sans-serif;" >
</p>
<div class="footer">
  Copyright &#169; 2022 CANVAS, Developed by Paarkavy B
</div>   
  <style>
h1{
    text-align: center;
    color: rgb(108, 60, 196);
}
center{
    font-size: 15px;

}
button{
    font-size: 30px;
}
#container{
    padding-left: 53em;
}
#myCanvas{
    background-color: #d3c5c5; 
    box-shadow: inset 0 0 5px #000000;
    backdrop-filter: blur(15px);
    border-radius: 10px;
    border: 1px solid #ffffff;
}
.button{
  font-size: 5px;
}
#keys{
    background-color: #8a7dd6c2;
    border: 2px solid rgb(255, 255, 255);
    border-radius: 25px;
    color: white;
    padding: 5px 5px;
    text-align: center;
    display: inline-block;
    font-size: 16px;
    margin: 4px 4px;
    cursor: pointer;
}
#keys:hover{
    background-color:#000000;
    transition: 0.1s;
}
#content{
  background:linear-gradient(75deg,rgb(156, 42, 131),rgb(186, 199, 114));
}
.footer {
  display: block;
  width: 100%;
  height: 40px;
  background-color: #709bb8;
  font-size: 20px;
  text-align: center;
  padding-top: 10px;
  margin: 0px 0px 0px 0px;
  color: #bd2779;
}
#colour{
         border: 2px solid #c3ddd3;
        border-radius: 25px;
        padding: 25px 25px;
        text-align: center;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        }
#colour:hover{
            opacity: 10%;
            transition: 0.1s;
        }
  </style>  
<div><h2><marquee>Thank For Visiting Our Page</marquee</h2></div>
</div>
</body>
</html>
```

## OUTPUT:

BLANK CANVAS:
![canvas1](https://user-images.githubusercontent.com/93509383/150690844-b132dc69-18d4-43d3-85cf-a8fa4dfcb1ce.png)

SIZE CHANGE:
![canvas2](https://user-images.githubusercontent.com/93509383/150690856-cf5b0e72-25f6-4917-9bfb-30f207ca1beb.png)

DRAWN CANVAS:

![canvas](https://user-images.githubusercontent.com/93509383/150690827-451d88c6-840f-443e-8a60-55d39f99d898.png)



## Result:

Thus a website is designed and validated for paint application using HTML5 canvas.
