+++
archetype = "chapter"
title = "5. npm e instalar módulos externos"
weight = 5
+++

## npm
Módulos que la gente ha creado

`npm init` inicializa un proyecto node. Responder a las preguntas:
- package name: learning-npm
- description: im learning about npm
- author: gino liza

Genera `package.json` un archivo de configuración

## Instalar paquete npm
Desde [npmjs.com](https://www.npmjs.com/), buscar [sillyname](https://www.npmjs.com/package/sillyname) e instalarlo con `npm i sillyname`. Esto agrega una linea a `package.json` debajo de `dependencies`

{{< highlight type="json" wrap="true" title="package.json">}}
  "dependencies": {
    "sillyname": "^0.1.0"
  },
{{< /highlight >}}

{{< highlight type="js" wrap="true" title="index.js">}}
var generateName = require('sillyname');
var sillyName = generateName();

console.log(sillyName);
{{< /highlight >}}

## CJS vs ESM 
Especificar cual se quiere usar modificando `package.json`. La diferencia en `index.js` es:
- CJS: `commonjs` usa `require`
- ESM: `module` usa `import`
### Common Javascript (CJS)
```json
  {
  "type": "commonjs",
  }
```

```js
var generateName = require('sillyname');
```

### ECMAScript Módule (CSM)
```json
  {
  "type": "module",
  }
```

```js
import generateName from "sillyname";
```

## Reto
1. Instalar e importar el módulo superheroes
2. Imprimir

{{% expand title="Solución"%}}
1. [superheroes](https://www.npmjs.com/package/superheroes)
2. `npm i superheroes`

```js
import {randomSuperhero} from 'superheroes';

const name = randomSuperhero();

console.log(`I am ${name}`);
```

No olvidar de especificar `"type": "module",` en `package.json`

{{% /expand %}}