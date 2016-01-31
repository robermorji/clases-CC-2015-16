**Instala Vagrant en tu sistema**

Dado que vagrant por defecto usa virtualbox para administrar la virtualización, nos los descargamos.

```sudo apt-get install virtualbox```

A continuación descargamos vagrant usando ```apt-get`` dado que no se distribuye ya como una gema. En caso de tenerlo previamente instalado con una gema se recomiendo desintalarlo primero ```sudo gem uninstall vagrant```.

```sudo apt-get install vagrant```

Instalar ahora el paquete dkms para asegurarnos de que los módulos del kernel de Virtualbox están correctamente actualizados.

```sudo apt-get install virtualbox-dkms```

**Baja el "box" del ejemplo (precise64.box)**

En la página web de [vagrantbox](http://www.vagrantbox.es/) encontramos todas las máquinas. Al usar virtualbox buscamos la box de precise64 con dicho proveedor.

Descargamos y despleguamos la máquina : 

```vagrant box add ubuntu_precise http://files.vagrantup.com/precise64.box```
