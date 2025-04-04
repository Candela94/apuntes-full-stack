

# Apuntes-full-stack


## JavaScript

Lenguaje de programación de alto nivel, interpretado dinámicamente tipado
Puede operar en dos modos: 
- Floppy Mode: más permisivo y tolerante con ciertos errores, autocorrigiéndolos en tiempo de ejecución
- use strict: introduce restricciones adicionales y convierte algunos errores silenciosos en errores explícitos, facilitando la detección de problemas en las etapas iniciales del desarrollo.

### Scope 
Define desde dónde se puede acceder y manipular las variables y constantes 
- Global: declaradas fuera de la función, accesbles en cualquier parte del script 
- Local : declaradas dentro de una función. Se crean cuando se ejecuta la función y se eliminan cuando se ha completado 
- Bloque: constantes declaradas dentro de bloques, como condicionales o bucles for. Sólo funcionan dentro de él 


## Terminal 
Es una herramiento que nos permite, mediante comandos, interactuar con el sistema operativo. Nos permite gestionar archivos, carpetas, procesos... e incluso editar nuestro código. Cada sistema operativo tiene su propia terminal

Sirven para
- Sistema de gestión de dependencias (NPM)
- Trabajar con Bundling, testing y frameworks
- Crear y gestionar aplicaciones mediante el CLI (Command Line Interface)
- Uso de GIT

### Movimientos entre directorios 

```bash

cd nombre #Entrar a una carpeta
cd ncarpeta/nombre #Enrrar a una carpeta dentro de otra
cd .. #Salir de la carpeta 
cd ../.. #Salir de dos carpetas 
cd / #Ir a la raíz del sistema 
cd "Mi carpeta" #Entrar a una carpeta con espacios en el nombre 
D: #Cambiar de unidad al disco 

```


### Crear y eliminar carpetas 

```bash

mkdir nombre #Crear una carpeta 
rmdir nombre #Eliminar una carpeta 
rm -rf nombre-carpeta #Eliminar carpeta + su contenido 

```


### Ver contenido de una carpeta 

```bash

ls #Ver contenido 
ls -a #ver contenido incluyendo archivos ocultos
ls -l #Ver contenido en formato largo 
ls -la #Combina -l y -a 

```



## NodeJs - NPM 

NPM es el sistema de gestión de paquetes por defecto para node.js. Permite gestionarlos, actualizarlos, eliminarlos... siempre dentro de node_modules

### Instalar un paquete 

```bash

npm i nombre

#Global, en otdo el ordenador, usar en todas las carpetas y proyectos
npm i nombre --global
npm i -g

#Desarrollo, solo en el proyecto, mientras trabajamos 
npm i nombre --save-dev
npm i nombre -D

```

- Librerías de producción: se envían al navegador y se instalan en "dependencies" en json. 
- Librerías globales: las usamos en todo el ordenador. Solo funcionan en el entorno de desarrollo 
- Librerías de desarrollo: las usamos para trabajar y se instalan en devDependencies. No se envían al navegador, funcionan en el entorno de desarrollo

### Versiones

```js 

"dependencies": {
    "nombre-paquete": "^1.2.0" // Actualizable a 1.X.Y
    "nombre-paquete": "~1.2.0" // Actualizable a 1.2.X
    "nombre-paquete": "1.0.0" // Exacta
    "nombre-paquete": ">1.0.0" // todas las versiones mayores a 1.0.0
    "nombre-paquete": "<1.0.0" // todas las versiones menores a 1.0.0
    }

```



### Paquetes instalados 

```bash

npm list -g --depth 0
# - g --global nos muestran los paquetes glopales
# --depth 0 indica que NO muestra las dependencias, solo los paquetes principales 



#Desinstalar paquetes locales 
npm uninstall nombre 

#Desinstalar paquetes globales 
npm uninstall nombre --global 


```


## Package.json
Archivo que contiene toda la info de nuestro proyecto


```bash 

npm init 
npm i nodemon -D

#"build": "node index"   "dev":"nodemon index"

index.js

npm run dev


```

## Vite 

Tiene como objetico proporcionar una experiencia de desarrollo más rápida y ágil para proyectos web modernos. Posee frameworks y librerías (Vanilla, Vue, React...)




## Fetch 

### Request 
Petición y obtención de información de un servidor. puede ser sincrónica o asincrónica. Se usa para traer informacion JSON
Se utilizan para 
- Enviar datos a un servidor 
- Recibir datos de manera asíncrona 
- Promesas 

### Respuesta/response 
Es la información que nos devuelve el servidor. Recibimos una Promise que nos devuelve un objeto Response del cual podemos obtener la info que necesitamos con su método (.json() o .text())


### Promesa
Valor con métodos asociados, el cual nos promete que recibiremos un valor en el futuro. Tiene dos callbacks: resolve(exito) y reject(error)

Sus estados son:
- Pending. Estado inicial, ni cumplido ni rechazado 
- Fulfilled: Se ha cumplido 
- Rejected: No se ha cumplido 




## Variables de entorno
Son valores que se pueden configurar en el sistema operativo. Se utilizan para configurar el entorno de ejecución de una aplicación.
Son necesarias para configurar el entorno de ejecución de una aplicación de forma dinámica, lo que permite que una aplicación pueda ejecutarse en distintos entornos sin tener que modificar su código fuente, lo que facilita su mantenimiento

`DOTENV` nos permite cargar variables de entorno desde un archivo .env


### Expresiones regulares 

Secuencia de caracteres que forman un patrón de búsqueda. Se usan para buscar, manipular,  reemplazar o validar cadenas de texto

```js

// Usando el constructor RegExp
const regex1 = new RegExp('patrón');
// Escribiendo la expresión regular directamente
const regex2 = /patrón/;

// Usando el constructor RegExp para incluir una variable
const miNombre = "Lucía";
const regex3 = new RegExp("soy :"+ miNombre);

```


#### Flags en expresiones regulares 

- i: ignora mayusculas y minúsculas 
- g: encuentra todas las coincidencias, no solo la primera 
- m: multilinea, permite que "^"(inicio de la cadena) y "$"(final de la cadena) coincidan, y no solo en frente de toda la cadena 

- . : Cualquier carácter, excepto nueva línea 
- + : coincide con 1 o más repeticiones del carácter anterior 
- ?: coindice con 0 o 1 repetición del carácter anterior 
- | : operador OR, coindice con uno u otro patrón

### Clases de caracteres en expresiones regulares
Las clases de caracteres son un conjunto de caracteres que se pueden utilizar para buscar coincidencias. Algunas de las clases de caracteres más comunes son:

- \d: Cualquier dígito.
- \w: Cualquier carácter alfanumérico.
- \s: Cualquier espacio en blanco.
- \D: Cualquier carácter que no sea un dígito.
- \W: Cualquier carácter que no sea alfanumérico.
- \S: Cualquier carácter que no sea un espacio en blanco.

Podemos definir también la cantidad de caracteres que queremos buscar utilizando llaves {}. Por ejemplo, /hola{2}/ buscará hola seguido de dos a. o /\w{2,4}/ buscará todas las palabras que tengan entre 2 y 4 caracteres.