<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EcoSemáforo</title>

<style>

body{
    margin:0;
    font-family:Arial,sans-serif;
    background:linear-gradient(135deg,#c8f7c5,#ecfff0);
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}

.caja{

    background:white;
    width:360px;
    padding:30px;
    border-radius:20px;
    box-shadow:0 10px 25px rgba(0,0,0,.2);
    text-align:center;

}

h1{

color:#2e7d32;

}

select{

width:100%;
padding:12px;
font-size:18px;
border-radius:10px;

}

button{

margin-top:20px;
padding:14px;
width:100%;
background:#2e7d32;
color:white;
border:none;
font-size:18px;
border-radius:10px;
cursor:pointer;

}

button:hover{

background:#1b5e20;

}

#resultado{

margin-top:25px;
padding:20px;
border-radius:15px;
display:none;

}

#emoji{

font-size:70px;

}

#titulo{

font-size:30px;
font-weight:bold;

}

#mensaje{

font-size:18px;

}

</style>

</head>

<body>

<div class="caja">

<h1>♻️ EcoSemáforo</h1>

<p><b>Selecciona el residuo que deseas desechar.</b></p>

<select id="residuo">

<option>Botella de plástico</option>

<option>Papel</option>

<option>Cartón</option>

<option>Lata</option>

<option>Vidrio</option>

<option>Orgánicos</option>

<option>Envase sucio</option>

<option>Pilas</option>

<option>Electrónicos</option>

<option>Otro</option>

</select>

<button onclick="verificar()">

Verificar

</button>

<div id="resultado">

<div id="emoji"></div>

<div id="titulo"></div>

<p id="mensaje"></p>

</div>

</div>

<script>

function verificar(){

let r=document.getElementById("residuo").value;

let caja=document.getElementById("resultado");

let emoji=document.getElementById("emoji");

let titulo=document.getElementById("titulo");

let mensaje=document.getElementById("mensaje");

caja.style.display="block";

if(
r=="Botella de plástico"||
r=="Papel"||
r=="Cartón"||
r=="Lata"||
r=="Vidrio"
){

caja.style.background="#d4edda";

titulo.style.color="green";

emoji.innerHTML="🟢";

titulo.innerHTML="¡Correcto!";

mensaje.innerHTML="Este residuo puede reciclarse correctamente. ¡Gracias por cuidar el planeta! 🌎";

}

else if(

r=="Envase sucio"

){

caja.style.background="#fff3cd";

titulo.style.color="#b8860b";

emoji.innerHTML="🟡";

titulo.innerHTML="Revisa";

mensaje.innerHTML="Antes de reciclar este residuo debes limpiarlo para evitar contaminar otros materiales.";

}

else if(

r=="Orgánicos"

){

caja.style.background="#fff3cd";

titulo.style.color="#b8860b";

emoji.innerHTML="🟡";

titulo.innerHTML="Revisa";

mensaje.innerHTML="Los residuos orgánicos deben depositarse en un contenedor para composta o residuos orgánicos.";

}

else if(

r=="Pilas"||

r=="Electrónicos"

){

caja.style.background="#f8d7da";

titulo.style.color="red";

emoji.innerHTML="🔴";

titulo.innerHTML="Incorrecto";

mensaje.innerHTML="Este residuo requiere un manejo especial. Debe llevarse a un centro de acopio.";

}

else{

caja.style.background="#eeeeee";

titulo.style.color="black";

emoji.innerHTML="❓";

titulo.innerHTML="Información no disponible";

mensaje.innerHTML="Consulta cómo desechar correctamente este residuo.";

}

}

</script>

</body>
</html>