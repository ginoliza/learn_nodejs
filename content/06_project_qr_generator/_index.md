+++
archetype = "chapter"
title = "6. Proyecto - Generador de QRs"
weight = 6
+++

#

1. Usar el paquete npm `inquirer` para obtener la entrada de usuario
2. Usar el paquete npm `qr-image` para convertir la URL que ingresa el usuario a una imagen QR
3. Crear un archivo txt para guardar la entrada de usuario usando el modulo nativo de node `fs`
   <br>

{{% expand title="solucion"%}}

1. Inicializar el proyecto con `npm init` (en caso se haya instalado los paquetes primero, se puede correr igualmente y llenará las dependencias en `package.json`)
2. Instalar inquirer y qr-image ```npm i @inquirer/prompts qr-image``` (esta es la nueva version de inquirer)


```js
var inq = require("@inquirer/prompts");
var qr = require("qr-image");
var fs = require("fs");

async function generate_qr() {
  // Ingresar URL
  const answer = await inq.input({ message: "Ingrese URL:" });

  // Convertir texto a qr png
  var qr_png = qr.image(`${answer}`, { type: "png" });
  qr_png.pipe(fs.createWriteStream("i_love_qr.png"));

  // Guardar URL en un .txt
  fs.writeFile("URL.txt", `${answer}`, (err) => {
    if (err) throw err;    
  });
}

generate_qr();
```
La función es asíncrona debido a que es necesario usar `await`. En caso se desee `imports` modificar `package.json` agregando `"type": "module"`
{{% /expand %}}

