# Ejercicio
## 1. Instalar a partir de docker una imagen alternativa de Ubuntu y alguna adicional, por ejemplo de CentOS.
Antes de poder instalar una imagen con Docker, tendremos que añadir nuestro usuario a su grupo:

```
sudo usermod -aG docker $USER
```

Podemos encontrar una gran cantidad de imagenes para Docker en su propio [repositorio](https://hub.docker.com/). Por ejemplo podemos instalar [esta](https://hub.docker.com/r/dorowu/ubuntu-desktop-lxde-vnc/) imagen de Ubuntu que integra OpenSSH y NoVNC; una vez que se haya terminado de descargar, la arrancamos.

```
docker pull dorowu/ubuntu-desktop-lxde-vnc
docker run -i -t -p 6080:6080 dorowu/ubuntu-desktop-lxde-vnc
```

Como el puerto que hemos indicado en el que arranque es el **6080**, si abrimos nuestro navegador y accedemos a la dirección [127.0.0.1:6080](127.0.0.1:6080) podremos acceder a la máquina con NoVNC mediante nuestro navegador.

Para loguearnos en una sesión por defecto solo tenemos que dejar el campo de contraseña vacio y pulsar **Connect**.

En cuanto a la imagen con CentOS, se haría de la misma forma por ejemplo con [esta imagen](https://hub.docker.com/r/berngp/docker-zabbix/) de CentOS con Zabbix instalado.

```
docker pull berngp/docker-zabbix
sudo docker run -d -p 10051:10051 -p 10052:10052 -p 80:80 -p 2812:2812 --name dockbbix berngp/docker-zabbix
```

Accesible también desde el navegador introduciendo la dirección del host local y el puerto al que hayamos indicado que vamos a redirigir el puerto 80 de la máquina Docker (recordando usar `sudo` si vamos a usar el puerto **80** al ser este un puerto protegido).

Si tenemos interés de probarlo, el usuario por defecto es **admin** y la contraseña **zabbix**.

## 2. Buscar e instalar una imagen que incluya MongoDB.
Si queremos instalar una imagen que incluye MongoDB podemos descargar la [imagen oficial](https://hub.docker.com/_/mongo/) que hay en Docker Hub. Podemos arrancar el demonio de MongoDB y ver como la imagen está arrancada.

```
docker pull mongo
docker run --name mongocker -d mongo
docker ps
```
