#Ejercicio 3

Crear pruebas para las diferentes rutas de la aplicaci—n (Programa de Calificaci—n de Empresas).
 
###Pasos realizados para la resoluci—n del ejercicio:

1. Se define una estructura de aplicaci—n _web_ utilizando _Express_

 `express calificacionEmpresas_2`
 
2. Se actualiza el archivo [index.js](https://github.com/jfrancisco4490/calificacionEmpresa_2/blob/master/routes/index.js) con la definici—n de las posibles operaciones soportadas en la aplicaci—n. Estas operaciones son:

 - `PUT /empresa/<id>/<nombre>/<direccion>/<area>` que define una solicitud de creaci—n de nueva empresa (enviando todos los par‡metros asociados a la misma)
 - `PUT /calificacion/<empresa>/<alumno>/<valor>` que especifica la creaci—n de una nueva calificaci—n de alumno a empresa
 - `DELETE /calificacion/<empresa>/<alumno>` que indica la eliminaci—n de una calificaci—n ya registrada en la base de datos
 - `GET /ranking` que define el listado de las empresas mejor valoradas segœn las calificaciones de los alumnos
 - `GET /calificaciones/<empresa>` que especifica el listado de todas las calificaciones de alumnos asociadas a una determinada empresa
 
3. Se actualiza el archivo [test.js](https://github.com/jfrancisco4490/calificacionEmpresa_2/blob/master/test/test.js) con la especificaci—n de las nuevas pruebas unitarias del sistema, utilizando la librer’a _supertest_. Se incluye una prueba de Žxito para cada funcionalidad implementada.

4. Se incluyen en el archivo [package.json](https://github.com/jfrancisco4490/calificacionEmpresa_2/blob/master/package.json) las librer’as de desarrollo correspondientes (especialmente _Express_ y _supertest_).

La estructura general del ejercicio se puede ver en el repositorio correspondiente: [Calificaci—n Empresas 2](https://github.com/jfrancisco4490/calificacionEmpresa_2)