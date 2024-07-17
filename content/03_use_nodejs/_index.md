+++
archetype = "chapter"
title = "3. Usar node.js"
weight = 3
+++

## Verificar la version de node
`node -v`

## REPL
Read Eval Print Loop: entorno para correr código en la terminal. Salir con `.exit` o `Ctrk+C` dos veces

```js
3+5 // 8

let a=12
a // 12
```

## Correr archivos JS
{{< highlight type="js" wrap="true" title="index.php">}}
console.log("hello world!");
{{< /highlight >}}

{{< highlight type="bash" wrap="true" title="terminal">}}
node index.js
{{< /highlight >}}