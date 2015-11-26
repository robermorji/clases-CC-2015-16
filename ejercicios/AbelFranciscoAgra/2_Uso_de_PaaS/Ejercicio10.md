#Ejercicio 10

Realizar un peque–o programa, en el lenguaje elegido y sobre la base de datos "tradicional" elegida (_PostgreSQL_ o cualquier otro online) que realice el ciclo b‡sico de una base de datos. Puede ser la aplicaci—n de calificaci—n de empresas realizada anteriormente.

###Pasos realizados para la resoluci—n del ejercicio:

1. Se define un archivo de prueba, llamado [_testPostgreSQL.js_](https://github.com/JJ/clases-CC-2015-16/blob/master/ejercicios/AbelFranciscoAgra/2_Uso_de_PaaS/testPostgreSQL.js), con algunas pruebas de las funcionalidades b‡sicas de un servicio de base de datos (Consultas, Registros, Actualizaciones y Eliminaciones), utilizando _node.js_.

 Las pruebas que implementa el programa anterior son:
 
 - Creaci—n de nueva empresa
 - Registro de nuevo alumno
 - Definici—n de nueva calificaci—n
 - Ranking de empresas
 - Listado de calificaciones de una empresa
 - Actualizaci—n de calificaci—n ya registrada
 - Eliminaci—n de calificaci—n
 
**Nota:** Para ejecutar el programa:
  
- Instalar la dependencia _node-postgres_ utilizando _npm_
  
 `npm install pg --save`
   
- Actualizar el archivo _testPostgreSQL.js_ con el _string_ de conexi—n correspondiente a la instalaci—n de _PostgreSQL_ que se desee utilizar en las pruebas. El _string_ de conexi—n es de la forma:

 `postgres://<usuario>:<contrase–a>@<host>:<puerto>/<nombre_base_datos>`

- Iniciar el servidor _PostgreSQL_
  
 `postgres -D <directorio_instalacion_postgreSQL>`
   
- Ejecutar el esquema para calificaci—n de empresas. El esquema puede ser consultado [aqu’](https://github.com/jfrancisco4490/calificacionEmpresa_2/blob/master/db/creacionTablasBD.sql).

 `psql -d <nombre_base_datos> -f <archivo_definicion_esquema>`
 
 En `<nombre_base_datos>` se puede colocar un _string_ de conexi—n con el formato presentado anteriormente.
   
- Ejecutar `node testPostgreSQL.js` (o `npm start` si se ha configurado en el archivo _package.json_)
