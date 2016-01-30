**Instalar QEMU**


Para instalar la herramienta de virtualización QEMU, con sus componentes adicionales como las herramientas **virt-viewer** y **virt-manager** para gestionar las máquinas creadas mdiante un entorno gráfico, usamos el siguiente comando :

```sudo apt-get install qemu-kvm qemu virt-manager virt-viewer libvirt-bin```

**Bajar una distribución de Linux (p.ej. Debian )**


Nos descargamos una imagen iso de cualquier distribución útil. Para hacer pruebas son recomendables distribuciones de muy reducido peso como :

* Damn Small Linux
* SliTaz

Estos sistemas operativos basados en Linux ocupan cerca de 50 MB.

**Crear un disco virtualizado para QEMU**

Para crear los discos dondse se van a instlar los sistemas operativos propuestos usamos el siguiente comando :
 
```qemu-img create -f qcow2 <nombre_fichero> <tamanio_fichero>```

Por ejemplo :

```qemu-img create -f qcow2 slitaz.qcow2 1G```






