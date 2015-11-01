**José Cristóbal López Zafra - Ejercicios del [tema 2](http://jj.github.io/CC/documentos/temas/Contenedores)**

##Ejercicio1
###Instala LXC en tu versión de Linux favorita. Normalmente la versión en desarrollo, disponible tanto en GitHub como en el sitio web está bastante más avanzada; para evitar problemas sobre todo con las herramientas que vamos a ver más adelante, conviene que te instales la última versión y si es posible una igual o mayor a la 1.0

Podemos instalarlo con `sudo apt-get install lxc`, pero no nos aseguramos que sea la última versión.

Para asegurarnos que sí es la última versión: primero nos la descargamos de Github: `git clone https://github.com/lxc/lxc`

y en el directorio recién creado de LXC ejecutamos `./autogen.sh && ./configure && make && sudo make install`

Puede dar problemas si no tenemos instalado *autoconf*, que instalamos con `sudo apt-get install autoconf`

Por último comprobamos si está preparado para usar este tipo de tecnología y también si se ha configurado correctamente con `lxc-checkconfig`:

![resultado de lxc-checkconfig](https://i.gyazo.com/2aa012ee5742ea2a98844cc5a42efacb.png)


##Ejercicio2
###Comprobar qué interfaces puente se han creado y explicarlos.



##Ejercicio3
####Crear y ejecutar un contenedor basado en Debian.

####Crear y ejecutar un contenedor basado en otra distribución, tal como Fedora. Nota En general, crear un contenedor basado en tu distribución y otro basado en otra que no sea la tuya. Fedora, al parecer, tiene problemas si estás en Ubuntu 13.04 o superior, así que en tal caso usa cualquier otra distro. Por ejemplo, Óscar Zafra ha logrado instalar Gentoo usando un script descargado desde su sitio, como indica en este comentario en el issue.


