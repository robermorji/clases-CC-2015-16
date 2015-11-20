**José Cristóbal López Zafra - Ejercicios del [tema 2](http://jj.github.io/CC/documentos/temas/PaaS)**

##Ejercicio1

###Darse de alta en algún servicio PaaS tal como Heroku, Nodejitsu, BlueMix u OpenShift.

 Accedemos a la web de [OpenShift](https://www.openshift.com/) y nos registramos.

[Dentro](http://i.imgur.com/pM22hgv.png) podremos gestionar nuestras aplicaciones o cambiar la configuración, por ejemplo.

##Ejercicio2
###Crear una aplicación en OpenShift y dentro de ella instalar WordPress. 

Dentro de OpenShift vamos al botón ["Add Aplication..."](https://openshift.redhat.com/app/console/application_types) para crear nuestra primera apliación.

Escogemos de la lista WordPress:

![lista de aplicaciones](https://i.gyazo.com/6d4c4b5a4f4c95317d32d871a5d3138f.png)

Escogemos el nombre que queremos, y nos queda:

![aplicación](http://i.imgur.com/AhXucv0.png)


Vamos a nuestra aplicación mediante el enlace que nos da y nos registramos en WordPress:

![WordPress](http://i.imgur.com/PfKMINP.png)

Y ya está instalado, configurado y disponible para publicar entradas:

![entrada0](http://i.imgur.com/6vm3VUi.png)

##Ejercicio3
###Crear pruebas para las diferentes rutas de la aplicación


##Ejercicio4
###Instalar y echar a andar tu primera aplicación en Heroku.

Instalamos el cinturon de heroku con `wget -O- https://toolbelt.heroku.com/install-ubuntu.sh | sh ` y `heroku login`

Nos logueamos y clonamos una [aplicación de ejemplo](https://github.com/heroku/node-js-getting-started): `git clone git@github.com:heroku/node-js-getting-started.git`.

La instalamos y arrancamos con `npm install` y `npm start`. Podemos ver que se está ejecutando en http://localhost:5000/

Y para desplegar en Heroku:

`heroku create`
`git push heroku master`
`heroku open`

Accedemos al [dashboard de Heroku](https://dashboard.heroku.com/apps) y comprobamos que [la hemos creado](https://i.gyazo.com/2b43b50d4da76fb9a65008b883217770.png).

En mi caso puedo ver la aplicación desplegada en: https://dry-meadow-8186.herokuapp.com/ 

##Ejercicio5
###Usar como base la aplicación de ejemplo de heroku y combinarla con la aplicación en node que se ha creado anteriormente. Probarla de forma local con foreman. Al final de cada modificación, los tests tendrán que funcionar correctamente; cuando se pasen los tests, se puede volver a desplegar en heroku.
####Como en todos los ejemplos anteriores, se puede cambiar “node” y “heroku” por la herramienta que se haya elegido.

Para probarla en local ejecutamos `foreman start web` (con `web: python script.py` dentro del archivo *Procfile*)

![preba con foreman](https://i.gyazo.com/76fc316245f393826a4522a19376d927.png)


Cremos la aplicación (especificando el buildpack python) en Heroku con `heroku apps:create --region eu --buildpack heroku/python periodicointeractivo-heroku1-1`.

![app creada](https://i.gyazo.com/cd7c6d39b1d23fb19f604b195379771d.png)

Después tendremos que modificar el *Procfile* para ajustar la ejecución de la aplicación. Primero nos lo descargamos `heroku git:clone -a periodicointeractivo-heroku1-1` y añadimos un archivo *Procfile* con `web: python script.py`. 

Guardamos cambios ( `git add Procfile` `git commit` y `git push heroku master`)

[Aplicación con cambios guardados](https://i.gyazo.com/44e75f6ee25b60a90b25415b12ae22c5.png)

##Ejercicio6
###Haz alguna modificación a tu aplicación en node.js para Heroku, sin olvidar añadir los tests para la nueva funcionalidad, y configura el despliegue automático a Heroku usando Snap CI o alguno de los otros servicios, como Codeship, mencionados en StackOverflow

Para trabajar con la aplicación de [ejemplo](https://github.com/heroku/node-js-getting-started) que hemos usado tenemos que borrar el origen inicial `git remote rm origin` y ajustar el de un repositorio propio con `git remote add origin git@github.com/JCristobal/node-js-getting-started.git`.

(O trabajar con [nuestro propio fork](https://github.com/JCristobal/node-js-getting-started))

Primero probaremos la [integración con GitHub](https://devcenter.heroku.com/articles/github-integration#enabling-github-integration): Nos vamos al panel de control y en Deploy seleccionamos "GitHub Connect to GitHub".

Seleccionamos el repositorio y continuamos, y nos queda:

![integracion github](https://i.gyazo.com/b00664dce5a814fb818830d0fa260727.png)

Debajo activamos los despliegues automáticos a la rama del respositorio que queramos.

Y dentro de GitHub (respositorio asociado) > Settings > Webhooks & Services, buscamos y añadimos el servicio de *HerokuBeta* y rellenamos los datos que piden.

[Aplicación con el despliegue automático después de algunos cambios](https://i.gyazo.com/30dfed21186ee73ef0bb152c9a60a338.png): https://dry-meadow-8186.herokuapp.com/


También pruebo con Snap CI. Para ello me registro con mi perfil de GitHub y escojo el repositorio en que estamos trabajando:

![snap test](https://i.gyazo.com/717a84beda6e5b3e25787403883753cf.png)

Podemos cambiar la [configuración](https://i.gyazo.com/242f28a9320467bae25916df52823c62.png), y para asociarlo con Heroku creamos un nuevo "Stage".

![snap heroku](https://i.gyazo.com/b17d0c5bb1fa5b2abb3cc098ef0ad2be.png)

![snap heroku passed](https://i.gyazo.com/9800997f2c13e1cfea4cbb986b38440c.png)








