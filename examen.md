

- La Temoral Dead Zone e cuando no se puede acceder en las variables let y const 
- A falta de configuración del objeto options, GET es el método que se utiliza por defecto 
- La propiedad body del objeto options del fetch sirve para enviar los datos de la petición
- useref devuelve un objeto con la propiedad current 
- $not en una consulta en mongoose compara si un campo es distinto a un valor especificado
. $gt compara si un campo es mayor que un valor especificado



- Exportar una función sumar por defecto
        - CommonJS
        module.exports = {sumar}

        Para importar, utiliza require()
        const {sumar} = require('ruta')

        Importar cambiando el nombre
        const {sumar:otroNombre} = require('ruta')



- Las variables let se pueden redeclarar: falso 


## Express

- app.listen() : Inicia el servidor en un puerto determinado, escuchando las solicitudes entrantes

- app.use() : Incorpora un middleware en la cadena de procesamiento de solicitudes 

- app.json() : Parsea el cuerpo de las solicitudes entrantes en formato JSON 

- app.static () : Sirve archivos estáticos (imagenes, css..) desde un directorio 

- app.all() : Define un manejador para todos los HTTP en una ruta específica

- app.get() : Define un manejador para solicitudes GET en una ruta específica

- app.post() : Define un manejador para solicitudes POST en una ruta específica, lo mismo con app.delete() y ap.put(), que manejan solicitudes DELETE y PUT



## MongoDB 

- .findbyId()  buscamos por su id 
- .find()  buscar elementos basados en las propiedades especificadas
- .find() sin argumentos   retorna todos los documentos de la colección 
- .limit() restringir el número de documentos devueltos en una consulta 
- .sort()  ordena los documentos devueltos según la propiedad especificada 
- .skip() omitir un número específico de documentos antes de devolver el resultado 
- select permite especificar qué campos se deben incluir o excluir en los documentos devueltos 



- para crear la carpeta dist y la versión de producción usamos el comando `npm run build`

