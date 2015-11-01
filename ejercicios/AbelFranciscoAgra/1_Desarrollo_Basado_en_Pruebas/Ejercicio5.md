#Ejercicio 5

Automatizar con _grunt_ y _docco_ (o algún otro sistema) la generación de documentación de la librería que se cree. Previamente, por supuesto, habrá que documentar tal librería.

###Pasos realizados para la resolución del ejercicio:

1. Documentar los archivos [_libCalificacionEmpresa.js_](https://github.com/jfrancisco4490/calificacionEmpresa/blob/master/src/lib/libCalificacionEmpresa.js) y [_testCalificacionEmpresa.js_](https://github.com/jfrancisco4490/calificacionEmpresa/blob/master/src/testCalificacionEmpresa.js).

2. Elaborar un archivo [_Gruntfile.js_](https://github.com/jfrancisco4490/calificacionEmpresa/blob/master/Gruntfile.js), con la especificación de la actividad para generar la documentación del código:

 a. Definir la tarea de documentación, tomando los archivos de código (_.js_) de la carpeta correspondiente (_src_), y generando la documentación asociada a cada archivo en el directorio designado para ello (_docs_)
 
 ```
 docco: {
	debug: {
		src: ['src/*.js'],
	  	options: {
			output: 'docs/'
	  	}
	}
 }
 ```
 
 b. Cargar el _plugin_ de _grunt_ para la ejecución de tareas
 
 `grunt.loadNpmTasks('grunt-docco');`
 
 c. Registrar tarea por defecto: generar la documentación del código
 
 `grunt.registerTask('default', ['docco']);`
 
 d. Ejecutar tarea de generación de documentación del código:
 
 `grunt docco`
 
 ```
 Running "docco:debug" (docco) task
 docco: src/libCalificacionEmpresa.js -> docs/libCalificacionEmpresa.html
 docco: src/testCalificacionEmpresa.js -> docs/testCalificacionEmpresa.html

Done, without errors.
 ```
 
 Los archivos de documentación generados son [_libCalificacionEmpresa.html_](https://github.com/jfrancisco4490/calificacionEmpresa/blob/master/docs/libCalificacionEmpresa.html) y [_testCalificacionEmpresa.html_](https://github.com/jfrancisco4490/calificacionEmpresa/blob/master/docs/testCalificacionEmpresa.html)
 
 [Enlace](https://github.com/jfrancisco4490/calificacionEmpresa/tree/master/docs) con el resto de la documentación generada para la aplicación. 