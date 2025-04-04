# React

Es una librería de Js de código abierto, diseñada para crear interfaces con el objetivo de facilitar el desarrollo de aplicaciones en una sola página 
- Creación de componentes reutilizables 
- JSX para crear interfaces de usuario. Permite escribir HTML dentro de JS
- Se puede trabajar con `clases`o con `funciones`(hooks)
- React developer tools es un plug in de chrome que nos permite inspeccionar los componentes de React en el navegador, y así poder ver el estado de los componentes, las props, árbol de componentes...


```bash

mi-proyecto             // nombre del proyecto
├── node_modules        // dependencias
├── public              // archivos de acceso público
└── src                 // código fuente de mi proyecto (js, jsx, css, etc)
    ├── assets          // archivos estáticos (imágenes, videos, etc)
    ├── components      // carpeta con componentes
    ├── ...             // otros archivos
    ├── App.jsx         // componente principal
    └── main.jsx        // archivo principal


├── .gitignore          // archivos ignorados por git
├── vite.config.js      // configuración de vite
├── ...                 // otras configuraciones
├── package-lock.json   // dependencias con versiones exactas
├── package.json        // Configuración del proyecto + lista de dependencias
└── index.html          // archivo principal

```


## Móduos en React 

Pequeños programas que se pueden reutilizar en otros programas. Son una parte de cualquier lenguaje, ya que proporcinan una forma de reutilizar el código, mantenerlo organizado y fácil de usar. 


### CommonJS


Archivo donde quiero exportar los componentes 

```js
// Exportación por defecto
module.exports = componente;
// Exportación de múltiples elementos
module.exports = { componente1, componente2, componente3 };
```

Archivo donde quiero importar los componentes 

```js
const componente = require("./ruta"); // importar un elemento por defecto
const { componente1, componente2, componente3 } = require("./ruta"); // importar múltiples elementos
const {
   componente1: alias1,
   componente2: alias2,
   componente3: alias3,
} = require("./ruta"); // importar múltiples elementos con alias

```


### ES Modules 

Archivo donde quiero exportar los componentes 

```js

// Exportación por defecto
export default componente;
// Exportación de múltiples elementos
export { componente1, componente2, componente3 };

```

Archivo donde importo los componentes 

```js

import componente from "./ruta"; // importar un elemento por defecto
import { componente1, componente2, componente3 } from "./ruta"; // importar múltiples elementos
import {
   componente1 as alias1,
   componente2 as alias2,
   componente3 as alias3,
} from "./ruta"; // importar múltiples elementos con alias

```


### Interpolación

Técnica que nos permite insertar valores de variables o expresiones de JavaScript dentro de un string. En react se usa para insertar valores de js dentro de los return


## Props 
Mecanismo para pasar datos de un componente padre a un hijo. Permiten que un hijo reciba valores o funciones desde el padre, lo que facilita la reutilización de componentes y la comunicación entre ellos 

- Son inmutables: una vez un componente recibe una prop, no puede ser modificada dentro del hijo. Si hay que cambiar el valor de una prop, se hace desde el padre 
- Se pasan de arriba hacia abajo. Los datos fluyen desde el padre al hijo 
- Pueden ser cualquier tipo de dato: cadenas, números, objetos, funciones, componentes... 
- Son como parámetros de una función: se pasan al componente en forma de un objeto 



#### Spread Operator 
Nos permite trabajar con los datos referenciales o compuestos. 

```js
// Ejemplo 2
let Alumno = { nombre: "Timmy" };
let nuevo = { ...Alumno };
Nuevo.edad = 33;
console.log(Alumno); // {nombre: 'Timmy', edad: 33}
console.log(Nuevo); // {nombre: 'Timmy', edad: 33}


//Ejemplo en props 

// Ejemplo
const props = {
   prop1: "valor1",
   prop2: "valor2",
   prop3: "valor3",
};
// método tradicional
<Componente prop1={prop1} prop2={prop2} prop3={prop3} />

// utilizando spread
<Componente {...props} />
```



## Hooks

Funciones que nos permiten agregar estado y otras características a los componentes funcionales. Nos permite reutilizar la lógica de estado y efectos entre componentes 

### useState
nos permite añadir estado a nuestro componente. Cuando realicemos un cambio en el estado, el componente se volverá a renderizar 
- el primer elemento es el valor del estado (estado de lectura)
- el segundo elemento es una funcion que nos permite actualizar ese estado 

