##Ejercicio 1
###Instala LXC en tu versión de Linux favorita. Normalmente la versión en desarrollo, disponible tanto en GitHub como en el sitio web está bastante más avanzada; para evitar problemas sobre todo con las herramientas que vamos a ver más adelante, conviene que te instales la última versión y si es posible una igual o mayor a la 1.0.

Para comenzar usamos el siguiente comando para instalar en mi ubuntu lxc: `sudo apt-get install lxc`

A continuación para comprobar que ha sido correctamente instalado tecleamos en la terminal: `lxc-checkconfig`

![Configuracion](https://gyazo.com/b54e53603099091a1c36742b88b5a8a6.png)

##Ejercicio 2
###Comprobar qué interfaces puente se han creado y explicarlos.

El comando que se usa para conocer los interfaces puentes es el siguiente:

`sudo brctl show`

![Puente](https://gyazo.com/e5d583524a29b61e884644cdf66967b9.png)

En este caso tengo creado dos interfaces puente, una es lxcbr0 que pertenece a LXC y la otra llamada docker0 que pertenece a docker, ambas con si id de puente pero sin ninguna interfaz enlazada al puente. Ya que no tenemos interfaces fisicas conectadas a ella.

##Ejercicio 3

Creamos con `sudo lxc-create -n debian -t debian -- -r jessie`	

##Ejercicio 4
###Instalar lxc-webpanel y usarlo para arrancar, parar y visualizar las máquinas virtuales que se tengan instaladas.

Para instalarlo tenemos que ejecutar la siguiente orden `wget http://lxc-webpanel.github.io/tools/install.sh -O - | bash`. Cuando termina la instalación podemos acceder a través de la siguiente URL http://localhost:5000

![Instalado](https://gyazo.com/b2f308d5c8a86966d0b311f921f01ebb.png)


###Desde el panel restringir los recursos que pueden usar: CPU shares, CPUs que se pueden usar (en sistemas multinúcleo) o cantidad de memoria.


Para cambiar los recursos de cada una de las máquina accedemos a su apartado y modificamos los recursos que se nos permitan modificar, como se muestra a continuación

![Configuracion](https://gyazo.com/58b7c9d58608b98ede424801d127d299.png)

##Ejercicio 6
###Instalar juju


Para instalar usamos el siguiente comando `sudo apt-get install juju-local`

###Usándolo, instalar MySQL en un táper.

Lo inicio con `juju init`. Se crea el fichero "environments.yaml": dentro cambiamos la línea `default: amazon` por default: local.

Se cambia a entorno local con `juju switch local`.

Se crea un contenedor con `juju bootstrap` y para instalar MySQL ejecutamos `juju deploy mysql`.


##Ejercicio 7

###Destruir toda la configuración creada anteriormente
Destruimos toda la configuración ejecutando juju destroy-environment local

###Volver a crear la máquina anterior y añadirle mediawiki y una relación entre ellos.

Creamos con juju bootstrap e instalamos MySQL `juju deploy mysql`. Añadimos mediawiki con `juju deploy  mediawiki` y la relación con `juju add-relation mediawiki:db mysql`. Para acabar exponemos el servicio `juju expose mediawiki`.

###Crear un script en shell para reproducir la configuración usada en las máquinas que hagan falta.

`#!/bin/bash

juju init

sed -i 's/default: amazon/default: local/g' ~/.juju/environments.yaml

juju switch local

juju bootstrap

juju deploy mysql

juju deploy mediawiki

juju add-relation mediawiki:db mysql

juju expose mediawiki`

##Ejercicio 8

##Instalar docker

Instalamos ejecutando sudo `apt-get install docker.io`

Y creamos un enlace a docker.io para poder usar simplemente docker como comando `sudo ln -sf /usr/bin/docker.io /usr/local/bin/docker`

##Ejercicio 11

###Crear a partir del contenedor anterior una imagen persistente con commit.


