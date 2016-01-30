#QEMU
##Instalar QEMU

Para instalar QEMU usamos el siguiente comando `sudo apt-get install qemu-kvm qemu virt-manager virt-viewer libvirt-bin`

##Bajar una distribución de Linux

Podemos bajarnos una distribución con wget o una imagen ya descargada como es en mi caso.

##Crear un disco virtualizado para QEMU

Para crearlo usamos `qemu-img create -f qcow2 debian-prueba.img 10G`

[DiscoCreado](https://gyazo.com/75214e189aa10e1bd7f401ea47e62278.png)

##Instalar Linux en dicho disco

Para instalar usaremos el siguiente comando `qemu-system-x86_64 debian_Prueba.img -boot d -cdrom ./Descargas/debian-8.3.0-i386-netinst.iso -m 640`


![Instalacion](https://gyazo.com/b8fda0218439acdd5e8cc0026b82329a.png)

##Ejecutar la máquina instalada para interaccionar con ella con su interfaz gráfica

La ejecutamos mediante qemu-system-x86_64 -hda qemu/debian-prueba.img

Interfaz gráfica de la máquina

##Ejecutar la máquina instalada sin interfaz gráfica, y entrar usando el cliente VNC

La arrancamos con sudo qemu-system-x86_64 -hda qemu/debian-prueba.img -vnc :1 y nos conectamos a ella mediante vncviewer 192.168.122.1:5901

Cliente VNC

##Instalar apache2 o nginx y probar que sirve páginas web (acceder desde el host a la IP del servidor virtualizado, bien con URL o con su navegador)

Vemos Apache arrancado, con un navegador en el anfitrión de la web servida.

Apache arrancado

##Microsoft Azure


#IBM Bluemix

##Crear una cuenta en Bluemix

El registro en Bluemix en en su web, de forma sencilla, rellenar el formulario y ya podemos acceder a la cuenta como se muestra en la siguiente captura:

![Bluemix](https://gyazo.com/dcae417c5976639eb2a2b8a14909f064.png)

##Desplegar una web sencilla

En este caso voy a desplegar en python una aplicación sencilla usada para el desarrollo de las prácticas de CC.
Para comenzar creo una aplicación web y con `./cf push PruebaEjercicio` subo mi programa desde la consola de comando CF

![Bluemix](https://gyazo.com/cbab40405ddbf4504f3bf14850af5fc2.png)


Para acceder a la web seguir el enlace http://pruebaejercicio.eu-gb.mybluemix.net/

Web desplegada 

![Pagina](https://gyazo.com/f0bf22728c39e9cb40cc6882e7d466e3.png)

##Monitorízala durante el tiempo que está en ejecución

Aquí podemos monitorear nuestra aplicación en ejecución

![Comofunciona](https://gyazo.com/f2f95ce457c206650d99952320b40ae5.png)



