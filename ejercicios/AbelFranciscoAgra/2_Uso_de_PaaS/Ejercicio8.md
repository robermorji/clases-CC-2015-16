#Ejercicio 8

Crear una aplicaci—n m’nima y usar un _buildpack_ no est‡ndar para desplegarla en _Heroku_.
 
###Pasos realizados para la resoluci—n del ejercicio:

1. Tras clonar el repositorio con el ejemplo de prueba de _Heroku_ para _node.js_, se crea la aplicacion y se le especifica el _buildpack_ a utilizar. En este caso, es un _buildpack_ que utilizar _Grunt_ para aplicar tareas sobre los procesos de compilaci—n, revisi—n de c—digo, etc.

 `heroku apps:create example-nodejs-buildpack --region eu --buildpack https://github.com/mbuchetics/heroku-buildpack-nodejs-grunt.git`

2. Actualizar la variable de entorno _NODE-ENV_, indicando que el ambiente es de producci—n:

 `heroku config:set NODE_ENV=production`

3. Definir un archivo _Gruntfile.js_ con una tarea espec’fica llamada _heroku_, de la siguiente manera:

 `grunt.registerTask('heroku:development', ['auto_install', 'jshint']);` (para ejecutar si el ambiente de despliegue es de desarrollo)
 `grunt.registerTask('heroku:production', ['auto_install', 'concat', 'uglify', 'jshint']);` (actividades a ejecutar si el ambiente es de producci—n)
 
4. A–adir dependencias de _Grunt_ en el _package.json_

 ```
   "dependencies": {
	...
    "grunt": "^0.4.5",
    "grunt-auto-install": "^0.3.0",
    "grunt-contrib-concat": "^0.5.1",
    "grunt-contrib-jshint": "^0.11.3",
    "grunt-contrib-uglify": "^0.10.0",
    ...
  }
 ```
 
5. Se despliega el repositorio (con el _Gruntfile.js_) a _Heroku_:

 `git push heroku master`
 
La aplicaci—n b‡sica de _node.js_ desplegada con el _buildpack_ no est‡ndar se puede acceder desde [aqu’](https://example-nodejs-buildpack.herokuapp.com/).

