# Ejercicio
## 1. Instalar `juju`.
Como vamos a trabajar en local, instalaremos `juju-local`, que además en las últimas versiones integra MongoDB con el paquete `juju-mongodb`.

```
sudo apt-get install juju-local
```

## 2. Usándolo, instalar `MySQL` en un táper.
Para usar **juju**, primero tenemos que inicializarlo con `juju init`, que crea el archivo con la información sobre las entornos de trabajo en `~/.juju/environments.yaml`.

Como vamos a trabajar en local, editamos dicho fichero y buscamos la línea `default: amazon` (configurado por defecto para trabajar con la nube de Amazon), cambiándolo a `default: local` para establecer que por defecto vamos a trabajar localmente, o también lo podemos hacer directamente con `sed -i 's/default: amazon/default: local/g' ~/.juju/environments.yaml`.

Antes de instalar MySQL, establecemos que vamos a trabajar en el entorno de trabajo local (`juju switch local`), como juju solo puede usar un contenedor que el mismo haya creado lo creamos (`juju bootstrap`).

Para instalar servicios dentro del contenedor, usamos los **charms** (script YAML para realizar tareas comunes) de los que no provee el propio sistema, concretamente el de para instalar **MySQL** (`juju deploy mysql`). Ya instalado comprobamos su estado con `juju status`, donde vemos que aparece la máquina anfitriona (**machine "0"**), el contenedor de juju (**machine "1"**) y como servicio instalado aparece **mysql**. Hsta que el contenedor de juju no esté totalmente preparado no dispondrá de ningún identificador y simplemente aparecerá **"pending"**.

Al par de minutos, la máquina ya será reconocida (en este caso como **germaaan-local-machine-1**), apareciendo como un contenedor más si los listados con `sudo lxc-ls --fancy`.
