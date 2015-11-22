#Ejercicio 5

Usar como base la aplicaci—n de ejemplo de _Heroku_ y combinarla con la aplicaci—n en _node.js_ que se ha creado anteriormente.
 
###Pasos realizados para la resoluci—n del ejercicio:

1. Actualizar las dependencias y complementos definidos en el _package.json_ de la aplicaci—n base de _Heroku_, para incluirlos en el archivos de configuraci—n correspondiente del programa de calificaci—n de empresas.

2. Definir un archivo [_Procfile_](https://github.com/jfrancisco4490/calificacionEmpresa_2/blob/master/Procfile), para la configuraci—n de la aplicaci—n en _Heroku_. En este caso, el _Procfile_ simplemente indica lo que se debe hacer para ejecutar la aplicaci—n _web_:

 `web: node routes/index.js`
