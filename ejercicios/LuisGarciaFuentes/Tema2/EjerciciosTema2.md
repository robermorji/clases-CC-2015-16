##Ejercicio1
###Darse de alta en algún servicio PaaS tal como Heroku, Nodejitsu, BlueMix u OpenShift.

El PaaS elegido a sido OpenShift en el cual nos podemos registrar en este [enlace](https://www.openshift.com/app/account/new).

![img](https://dl.dropboxusercontent.com/s/bdp8arnzmkpool4/CC-Tema2-Ejercicio1-1.png?dl=0)

Una vez logueado desde el panel de control ya podemos crear las aplicaciones que se necesiten.

![img](https://dl.dropboxusercontent.com/s/h12dsv1auoyfmjl/CC-Tema2-Ejercicio1-2.png?dl=0)


##Ejercicio2
###Crear una aplicación en OpenShift y dentro de ella instalar WordPress. 

Para la creación de una aplicación en OpenShift e instalar WordPress solo hay que seguir los siguientes pasos:

1. Accedemos al panel de control y accedemos a la pestaña **"Create you first aplication now"**.

![img](https://dl.dropboxusercontent.com/s/h12dsv1auoyfmjl/CC-Tema2-Ejercicio1-2.png?dl=0)

2.Como podemos ver en Instant App nos sale una versión de **"WordPress 4"** que será el que tenemos que seleccionar.

![img](https://dl.dropboxusercontent.com/s/nr326byzdgjvpfu/CC-Tema2-Ejercicio2-1.png?dl=0)

3.El único campo que tenemos que rellenar obligatoriamente es el **"Public URL"** que será la dirección web de nuestra App.

![img](https://dl.dropboxusercontent.com/s/56a9cho5qzdanjk/CC-Tema2-Ejercicio2-2.png?dl=0)

4.Como se puede ver en la imagen ya tenemos nuestra primera aplicación con WordPress instalada.

![img](https://dl.dropboxusercontent.com/s/qv1a2m2r05wsy8d/CC-Tema2-Ejercicio2-3.png?dl=0)

5.Para acceder a la aplicación por via web tenemos esta dirección [https://blogandroid-luishexen.rhcloud.com](https://blogandroid-luishexen.rhcloud.com).

![img](https://dl.dropboxusercontent.com/s/o9b42egayrnsud6/CC-Tema2-Ejercicio2-4.png?dl=0)


##Ejercicio3
###Realizar una aplicación básica que use express para devolver alguna estructura de datos del modelo que se viene usando en el curso.

###Realizar una app en express que incluya variables como en el caso anterior

###Crear pruebas para las diferentes rutas de la aplicación


##Ejercicio4
###Instalar y echar a andar tu primera aplicación en Heroku.

Lo primero que tenemos que hacer es registrarnos en la página de [Heroku](https://www.heroku.com/):

![img](https://dl.dropboxusercontent.com/s/cq7mh1ea4ngvdka/CC-Tema2-Ejercicio4-1.png?dl=0)

El siguiente paso es instalar ruby y el cinturón de herramientas de heroku:

```
sudo apt-get install ruby
```

```
wget -O- https://toolbelt.heroku.com/install-ubuntu.sh | sh
```

![img](https://dl.dropboxusercontent.com/s/qheg2nnrhu3q5t2/CC-Tema2-Ejercicio4-2.png?dl=0)

Para hacer login desde la terminal tenemos que usar el siguiente comando:

```
sudo heroku login
```

![img](https://dl.dropboxusercontent.com/s/u5ju06e2v4x0z22/CC-Tema2-Ejercicio4-3.png?dl=0)

Descargamos la aplicación de prueba hecha con Node.js desde su repositorio en GitHub y la desplegamos en Heroku:

```
git clone https://github.com/heroku/node-js-getting-started.git
cd node-js-getting-started
sudo heroku apps:create --region eu luis-cc-heroku
```

![img](https://dl.dropboxusercontent.com/s/q4q14vkf6ffr9tv/CC-Tema2-Ejercicio4-4.jpg?dl=0)

La aplicación ya está accesible siguiendo [este enlace](https://luis-cc-heroku.herokuapp.com/).


##Ejercicio5
###Usar como base la aplicación de ejemplo de heroku y combinarla con la aplicación en node que se ha creado anteriormente. Probarla de forma local con foreman. Al final de cada modificación, los tests tendrán que funcionar correctamente; cuando se pasen los tests, se puede volver a desplegar en heroku.
####Como en todos los ejemplos anteriores, se puede cambiar “node” y “heroku” por la herramienta que se haya elegido.


##Ejercicio6
###Haz alguna modificación a tu aplicación en node.js para Heroku, sin olvidar añadir los tests para la nueva funcionalidad, y configura el despliegue automático a Heroku usando Snap CI o alguno de los otros servicios, como Codeship, mencionados en StackOverflow


##Ejercicio7
###Preparar la aplicación con la que se ha venido trabajando hasta este momento para ejecutarse en un PaaS, el que se haya elegido. 


##Ejercicio8
###Crear una aplicación mínima y usar un buildpack no estándar para desplegarla en Heroku o un cartridge no estándar en OpenShift.


##Ejercicio9
###Instalar o darse de alta en un servicio Redis en la nube y realizar sobre él las operaciones básicas desde el panel de control.

###Instalar un cliente de línea de órdenes de Redis o un cliente REST y realizar desde él las operaciones básicas de creación y lectura de información.

###Ejecutar ejemplos de cualquier lenguaje de programación sobre la instalación realizada.

