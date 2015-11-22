#Ejercicio 4

Instalar y ejecutar una primera aplicaci—n en _Heroku_.
 
###Pasos realizados para la resoluci—n del ejercicio:

1. Instalar el _Heroku Toolbelt_, que provee acceso a la interfaz de L’nea de Comandos de _Heroku_. Esta interfaz puede ser utilizada para manejar y escalar las aplicaciones que se hayan desplegado. 

2. Iniciar sesi—n con la cuenta de _Heroku_ creada, utilizando el comando

 `heroku login`

3. Clonar la aplicaci—n de _node.js_ de prueba desde el repositorio correspondiente de _Heroku_

 `git clone https://github.com/heroku/node-js-getting-started.git`
 
4. Crear la aplicaci—n en _Heroku_, lo que lo prepara para recibir el c—digo fuente (y futuras modificaciones del mismo)

 `heroku apps:create --region eu example-nodejs`
 
5. Desplegar el c—digo en _Heroku_

 `git push heroku master`
 
6. Para ver la aplicaci—n desplegada accedemos a la _URL_ correspondiente. Se puede utilizar el comando:

 `heroku open`
 
La aplicaci—n de prueba desplegada se puede observar en el siguiente enlace: [https://example-nodejs.herokuapp.com](https://example-nodejs.herokuapp.com)

**Nota:** Con la aplicaci—n desplegada en _Heroku_, se pueden realizar cambios sobre el c—digo fuente y desplegar dichas modificaciones, instalar complementos para la aplicaci—n (_add-ons_), o incluso, ejecutarla localmente.