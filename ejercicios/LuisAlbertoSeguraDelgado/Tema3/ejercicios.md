# Ejercicios del Tema 3

### Ejercicio 1

LXC instalado y perfectamente configurado, simplemente ejecutando `sudo apt-get install lxc`

![](http://imgur.com/1i7scES.png)


### Ejercicio 2

![](http://imgur.com/YsCkZoP.png)
![](http://imgur.com/WTRm24U.png)

Una vez descargado todo lo necesario e instalado, como podemos ver en la imágenes anteriores, ya tenemos nuestro contenedor listo para funcionar.

En la siguiente captura podemos ver las nuevas interfaces que se han creado:

![](http://imgur.com/W7FIZOw.png)

Como vemos, se han creado las interfaces lxcbr0 y vethNb38rk. Ambas son puentes que permiten la conexión a internet desde nuestro contenedor. De esta forma podemos simular los habituales eth0 y lo que permiten la conexión a internet. Con estas interfaces nuevas que se crean, el contenedor tiene acceso a internet y tiene un conexión con el host, de forma que pueden comunicarse entre ellos si fuese necesario. Para ello, se crea un red local simulada entre el host y el contenedor, y a través de esa red local se permite la conexión a Internet por parte del contenedor.


### Ejercicio 3

Para instalar un contenedor basado en Fedora, simplemente ha sido necesario indicar el comando `sudo lxc-create -t fedora -n fedora`. El único problema que ha dado ha sido que necesitaba tener curl y yum instalados en mi sistema principal para poder crear el contenedor. Con un simple `apt-get install yum curl` todo se ha resuelto, he vuelto a ejecutar el comando para que crease el contenedor y listo.

En la siguiente imagen podemos ver el contenedor Fedora iniciado y funcionando.

![](http://imgur.com/JjBtMSF.png)

### Ejercicio 4

Para instalar LXC-Webpanel solamente hace falta ejecutar el comando: `wget https://lxc-webpanel.github.io/tools/install.sh -O - | bash`

![](http://imgur.com/ePtX0IJ.png)
![](http://imgur.com/umg2z9e.png)

Depués para limitar la cantidad de memoria que puede usar el contenedor o el número de CPUs, solamente debemos hacer click sobre el en el menú de la izquierda y configurar lo que deseemos.

![](http://imgur.com/IOy3mCd.png)
![](http://imgur.com/Ga3jLxF.png)

### Ejercicio 5

Comparar nginx contenedor vs host


### Ejercicio 6

Para instalar Juju solamente hace falta añadir el repositorio correspondiente con: `add-apt-repository ppa:juju/stable`. Y después instalar con: `sudo apt-get install juju-core juju-local` (antes hay que hacer un update, evidentemente).

Una vez instalado, hay que indicarle que configure todo con los siguiente comandos:

```
juju initjuju switch localjuju bootstrap
```

OJO: Después de juju init, debemos editar el fichero que genera (y que nos avisa que ha creado) y modificar la linea `default:amazon` por `default:local`.

Para Ubuntu 12.04 parece que hay algunos problemas con el paquete cloud-image-utils, por lo que es necesario añadir sus repositorios e intalarlo con:
```
add-apt-repository cloud-archive:tools
apt-get update
apt-get install cloud-image-utils
```

Finalmente, para crear un contenedor con MySQL, ejecutamos `juju deploy mysql`. Y finalmente acabamos con  `juju expose mysql`.

### Ejercicio 7

Para crear una relación entre una maquina MySQL y otra con MediaWiki, debemos primero crear cada una de ellas con: `juju deploy mysql` y `juju deploy mediawiki`.
Depués, debemos crear una relación entre ellas con `juju add-relation mediawiki:db mysql`.

Finalmente, acabamos con `juju expose mediawiki`.

Un script para reproducir la configuración usada quedaría del siguiente modo:

```
juju bootstrap
juju deploy mysql
juju deploy mediawiki
juju add-relation mediawiki:db mysql
juju expose mediawiki
```

Ya podemos ver la maquina en el panel web de LXC.

![](http://i.imgur.com/CnGMvq2.png)


### Ejercicio 8
