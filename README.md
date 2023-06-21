# laboratorio-3
El laboratorio tres se trata de crear tarjetas que contengan informacion aplicando los archivos json.

index.html
es el código que se utiliza para estructurar y desplegar una página web y sus contenidos. Por ejemplo, sus contenidos podrían ser párrafos,
una lista con viñetas, o imágenes y tablas de datos.

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laboratorio #3</title>
    <link rel="stylesheet" href="estilos.css">
</head>
<body>
    <h1>Tarjetas para revista digital con JSON
    <div id="tarjetas-container"></div>
    <script src="app.js"></script>
</body>
</html>
  
estilos.css
Las CSS (hojas de estilo en cascada) son archivos codificados que seleccionan elementos de tu página y controlan su presentación.
Piensa en el HTML de tu plantilla personalizada como los huesos del sitio web y la CSS como la piel.

.card {
    border: 1px solid #2d0139;
    border-radius: 8px;
    padding: 16px;
    margin-bottom: 16px;
    color: rgb(126, 6, 186);
}

.card h2 {
    font-size: 18px;
    margin-bottom: 8px;
}

.card p {
    font-size: 14px;
}
  
  
app.js 
JavaScript es un lenguaje de programación que los desarrolladores utilizan para hacer páginas web interactivas. Desde actualizar 
fuentes de redes sociales a mostrar animaciones y mapas interactivos, las funciones de JavaScript pueden mejorar la experiencia del 
usuario de un sitio web.
  
fetch ('data.json')
.then(response => response.json())
.then(data => {
const tarjetasContainer=document.getElementById('tarjetas-container');

data.forEach(objeto=>{
const tarjeta = document.createElement('div');
tarjeta.classList.add('card');

const titulo = document.createElement('h2');
titulo.textContent = objeto.titulo;
        
const contenido = document.createElement('p');
contenido.textContent = objeto.contenido;

tarjeta.appendChild(titulo);
tarjeta.appendChild(contenido);

tarjetasContainer.appendChild(tarjeta);
});
})
.catch(error => console.error(error));
  

data.json
El formato JSON (JavaScript Object Notation) es un formato abierto utilizado como alternativa al XML para la transferencia de datos 
estructurados entre un servidor de Web y una aplicación Web. Su lógica de organización tiene puntos de semejanza con el XML, pero 
posee una notación diferente.
  
[
    {
        "titulo": "Tarjeta #1",
        "contenido": "Contenido de la tarjeta #1"
    },
    {
        "titulo": "Tarjeta #2",
        "contenido": "Contenido de la tarjeta #2"
    },
    {
        "titulo": "Tarjeta #3",
        "contenido": "Contenido de la tarjeta #3"
    }

]
