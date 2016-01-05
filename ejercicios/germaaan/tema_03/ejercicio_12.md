# Ejercicio 12
## Crear una imagen con las herramientas necesarias para el proyecto de la asignatura sobre un sistema operativo de tu elección.
Las herramientas necesarias para el proyecto de la asignatura son básicamente **git** y el instalador de **Node.js**; el resto de dependencias se instalarán desde el propio proyecto. Por lo que el archivo Dockerfile será el siguiente:

```
# CC-Gesco-DatabaseManagement 1.0

FROM    ubuntu:latest
MAINTAINER German Martinez <germaaan@gmail.com> Version: 1.0

# Instalar todos los paquetes necesarios para poder realizar realizar el proyecto de CC
RUN apt-get -y install wget
RUN wget -qO- https://deb.nodesource.com/setup_4.x | sudo bash -
RUN sudo apt-get install -y git nodejs
RUN node -v
RUN git clone https://github.com/Gescosolution/Gesco-DatabaseManagement.git /home/Gesco-DatabaseManagement
RUN cd /home/Gesco-DatabaseManagement && npm install
```

Docker permite crear una imagen usando un Dockerfile almacenado en un repositorio GitHub, así que he creado [este repositorio](https://github.com/germaaan/Gesco-DatabaseManagement-Docker); por lo que además contaremos con que podemos aprovechar el control de versiones para las modificaciones que hagamos sobre el archivo para verlas reflejadas en la imagen a crear. Ahora solo queda crear la imagen:

```
docker build -t germaaan/gesco_databasemanagement -no-cache=true github.com/germaaan/Gesco-DatabaseManagement-Docker
```

Una vez la imagen ha terminado de crearse, podemos ver como aparece en el listado con el resto de imágenes:

```
docker images
```

Ahora queda comprobar que la imagen se ha creado correctamente iniciándola y verificando que todo lo indicado se ha instalado:

```
docker run -i -t germaaan/gesco_databasemanagement /bin/bash

# git --version
# node --version
# npm --version
# cd /home/Gesco-DatabaseManagement
# npm list --depth=0
```

Lo último que también podemos hacer es compartir la imagen que acabamos de crear, para lo que primero necesitaremos una cuenta en [Docker Hub](https://hub.docker.com/). Después, simplemente nos logueamos y subimos la imagen.

```
docker login
docker push germaaan/gesco_databasemanagement
```

 Cuando termine se creara una página de la imagen como [esta](https://hub.docker.com/r/germaaan/gesco_databasemanagement/).

Otra opción para añadir imágenes son los **automated builds**, imagenes que son construidas por el propio sistema de Docker usando un Dockerfile que tengamos en un repositorio de GitHub/Bitbucket, para lo cual primero deberemos enlazar nuestra cuenta (lo podemos hacer desde [aquí](https://hub.docker.com/add/automated-build/link-accounts/)). Una vez las cuentas estén vinculadas, tenemos que irnos a **Create -> Create Automated Build** en la página de Docker Hub, seleccionar el repositorio y crear la construcción automática.

Cuando se haya creado, aparecerá una página como [esta](https://hub.docker.com/r/germaaan/gesco-databasemanagement-docker/) en la que podemos ver que tenemos más menús que antes; como por ejemplo, _"Build Settings"_ para crear diferentes construciones de ramas de nuestro repositorio.
