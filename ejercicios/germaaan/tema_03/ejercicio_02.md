# Ejercicio 2
## Comprobar qué interfaces puente se han creado y explicarlos.
Para conocer los interfaces puente en nuestro sistema usamos `brctl`:

```
sudo brctl show
```

En mi caso no tengo más interfaces puente que _lxcbr0_ que es la interfaz puente que crea por defecto LXC, este puente está asignado a una interfaz llamada _vethO8OCUM_, una interfaz de red virtual (vIRTUAL ethERNET) enlazada con la interfaz física del sistema (_eth0_) para poder acceder a Internet a través de ella.
