# Ejercicio
## 1. Destruir toda la configuración creada anteriormente

Si queremos destruir una configuración, lo mejor es usar `sudo juju destroy-environment local` donde **local** es la configuración que queremos destruir, en caso contrario es muy posible que se produzcan errores.

## 2. Volver a crear la máquina anterior y añadirle mediawiki y una relación entre ellos.

Debemos volver a crear la configuración que teniamos antes de destruir todo:

```
juju bootstrap
sudo juju deploy mysql
```

Pero además añadiendole **MediaWiki** (`sudo juju deploy mediawiki`) y también una relación entre esta última máquina y la máquina con **MySQL** (`sudo juju add-relation mediawiki:db mysql`). Para terminar solo nos queda exponer el servicio para que sea accesible al público (`sudo juju expose mediawiki`).

Lo único que nos falta, es comprobar que verdaderamente funciona el servicio **MediaWiki** que hemos instalado, para eso tenemos que fijarnos en la dirección IP pública (**"public-address"**) asociada a la unidad del **MediaWiki** instalado que podemos ver en la salida del estado de **juju**, o también sabiendo en que máquina está, consultar su dirección IP (**"IPV4"**) en la tabla de máquinas existente de **LXC**. En cualquiera de los casos, una vez conozcamos la dirección IP debemos introducirla en un navegador y si todo funciona correctamente, accederemos a la página principal de **MediaWiki** con su configuración por defecto.

## 3. Crear un script en shell para reproducir la configuración usada en las máquinas que hagan falta.

```
#!/bin/bash
# Script para autoconfigurar juju con mysql y mediawiki en cualquier máquina

# Inicializar el entorno de juju
sudo juju init

# Seleccionar un entorno de trabajo local
sudo sed -i 's/default: amazon/default: local/g' ~/.juju/environments.yaml
sudo juju switch local

# Crear el contenedor juju
juju bootstrap

# Instalar mysql
sudo juju deploy mysql

# Instalar mediawiki
sudo juju deploy mediawiki

# Crear la relación necesaria entre mediawiki y mysql
juju add-relation mediawiki:db mysql

# Publicar el acceso al servicio mediawiki
juju expose mediawiki
```

Importante recordar que mientras que el estado de las máquinas mostrado con `sudo juju status` sea **pending** las máquinas no funcionaran; es necesario que el estado sea **started**.
