## Crear una cuenta en Bluemix.

Nos creamos una cuenta en Bluemix desde su [página de registro](https://console.ng.bluemix.net/registration/). Cuando finalizemos el registro y activemos la cuenta, podremos acceder sin mayor problema. (Nota: por algún motivo, el acceso con Google Chrome produce algunos problemas, usar Mozilla Firefox).

![eje01_img01](https://dl.dropboxusercontent.com/s/infry89hy7m3bo1/eje01_img01.png)

## Desplegar una aplicación web sencilla (elige el lenguaje).

Primero descargamos e instalamos la línea de comandos de Cloud Foundry para poder trabajar con nuestra cuenta de Bluemix desde una terminal.

```
wget http://go-cli.s3-website-us-east-1.amazonaws.com/releases/v6.15.0/cf-cli-installer_6.15.0_x86-64.deb && sudo dpkg -i cf-cli-installer_6.15.0_x86-64.deb
```

![eje02_img01](https://dl.dropboxusercontent.com/s/76ulripgfan3eu6/eje02_img01.png)

Como aplicación de prueba vamos a usar la aplicación de prueba en **Node.js** que crea el paquete `express` como ejemplo de su funcionalidad. Después de instalar el generador (`express-generator`), creamos la aplicación (`prueba`).

```
sudo npm install -g express-generator
express prueba
```

![eje02_img02](https://dl.dropboxusercontent.com/s/6zedbebl98voj53/eje02_img02.png)

Nos desplazamos al directorio que se ha creado para la aplicación e instalamos todas las dependencias de la aplicación.

```
cd prueba && npm install
```

![eje02_img03](https://dl.dropboxusercontent.com/s/h2mwzbwzw7y4mcg/eje02_img03.png)

Ahora solo nos queda arrancar la aplicación.

```
DEBUG=prueba:* npm start
```

![eje02_img04](https://dl.dropboxusercontent.com/s/9ghkz1475wq09ci/eje02_img04.png)

Si accedemos a la dirección [http://localhost:3000](http://localhost:3000), deberíamos encontrarnos la aplicación funcionando.

![eje02_img05](https://dl.dropboxusercontent.com/s/cf88wyscdrnvhdt/eje02_img05.png)

Lo siguiente que vamos a hacer es deplegar la aplicación en **Bluemix**, para ello lo primero que tenemos que hacer es conectar con Bluemix mediante su API (importante que nos conectemos a la API de la región donde tenemos nuestra cuenta albergada, en este caso la región es **Reino Unido** así que la API es **eu-gb**). Una vez hayamos conectado, tendremos que iniciar sesión con nuestra cuenta, indicando además el nombre del espacio donde desplegar nuestra aplicación (`dev`).

```
cf api https://api.eu-gb.bluemix.net
cf login -u germaaan@gmail.com -o germaaan@gmail.com -s dev
```

![eje02_img06](https://dl.dropboxusercontent.com/s/ttxjxv5zatkukt5/eje02_img06.png)

Ahora desde el directorio de nuestra aplicación, la desplegamos con la orden `push`, indicando además la cantidad de memoria de la que dispondrá la aplicación (`512m`).

```
cf push germaaancc -m 512m
```

![eje02_img07](https://dl.dropboxusercontent.com/s/3p5i42hso8pkyl7/eje02_img07.png)

Cuando termine el despliegue de la aplicación, el cliente nos informará si este ha sido correcto, además de diversas propiedades del despliegue de nuestra aplicación de la que ahora la que más nos interesa es la dirección de acceso (`URL`).

![eje02_img08](https://dl.dropboxusercontent.com/s/hoqu3bu0t73dh7f/eje02_img08.png)

Para comprobar que el despliegue ciertamente ha sido exitoso, accedemos a la dirección que nos indicaba el cliente al finalizar el despliegue: [http://germaaancc.eu-gb.mybluemix.net](http://germaaancc.eu-gb.mybluemix.net).

![eje02_img09](https://dl.dropboxusercontent.com/s/iaui3wwwovll5e9/eje02_img09.png)

## Modifica y actualiza tu aplicación.

## Monitorízala durante el tiempo que está en ejecución.

## Opcional: crea una máquina virtual, y accede a ella para instalar y configurar un servidor web.
