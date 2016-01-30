[José M. Rodríguez](https://github.com/Jmrodriguez90)

Uso de sistemas de virtualización: Ejercicio 1
======================================================================

1. Crear varias máquinas virtuales con algún sistema operativo libre, Linux o BSD. Si se quieren distribuciones que ocupen poco espacio con el objetivo principalmente de hacer pruebas se puede usar CoreOS (que sirve como soporte para Docker) GALPon Minino, hecha en Galicia para el mundo, Damn Small Linux, SliTaz (que cabe en 35 megas) y ttylinux (basado en línea de órdenes solo).
2. Hacer un ejercicio equivalente usando otro hipervisor como Xen, VirtualBox o Parallels.

--

Lo primero por hacer fue descargar una imagen del sistema, en este caso, coreOS con el siguiente comando:

`wget http://stable.release.core-os.net/amd64-usr/current/coreos_production_iso_image.iso`

Luego se pasó a crear una unidad de disco duro virtual con este comando:

`qemu-img create -f qcow2 coreos_prueba1.img 0.5G`

Y por último, instalar el sistema en qemu-kvm de la siguiente manera:

`qemu-system-x86_64 -hda coreos_prueba1.img -boot d -cdrom coreos_production_iso_image.iso -m 640`

Se hizo lo mismo con VirtualBox, en un ambiente gráfico lo cual tardó más puesto que había que realizar una creación guiada del disco duro y de la instalación del sistema, mientras que con la terminal, con unas cuantas líneas de comando se pudo hacer lo mismo con mucho mayor velocidad.
