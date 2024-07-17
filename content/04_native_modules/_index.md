+++
archetype = "chapter"
title = "4. Módulos nativos"
weight = 4
+++

Código existente que viene incluido en nuestra instalación de `node`

## File System (fs)

### writeFile
La función `writeFile` del módulo `fs` acepta tres parámetros:
1. El archivo al cual escribir
2. El contenido
3. Una función callback para manejar errores

{{< highlight type="js" wrap="true">}}
const fs = require("fs");

fs.writeFile('message.txt', "testing fs.writefile", (err) => {
  if (err) throw err;
  console.log('The file has been saved!');
});
{{< /highlight >}}

### readFile
Reto: modificar manualmente el archivo que acabamos de crear, y leerlo

{{% expand %}}

```js
fs.readFile("message.txt", "utf8", (err, data) => {
  if (err) throw err;
  console.log(data);
});

```
{{% /expand %}}

