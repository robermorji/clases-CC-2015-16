##Ejercicio 1
###Instala LXC en tu versión de Linux favorita. Normalmente la versión en desarrollo, disponible tanto en GitHub como en el sitio web está bastante más avanzada; para evitar problemas sobre todo con las herramientas que vamos a ver más adelante, conviene que te instales la última versión y si es posible una igual o mayor a la 1.0.

Para comenzar usamos el siguiente comando para instalar en mi ubuntu lxc: `sudo apt-get install lxc`

A continuación para comprobar que ha sido correctamente instalado tecleamos en la terminal: `lxc-checkconfig`

![Configuracion](https://gyazo.com/b54e53603099091a1c36742b88b5a8a6.png)

##Ejercicio 2
###Comprobar qué interfaces puente se han creado y explicarlos.

El comando que se usa para conocer los interfaces puentes es el siguiente:

`sudo brctl show`

![Puente](https://gyazo.com/e5d583524a29b61e884644cdf66967b9.png)

En este caso tengo creado dos interfaces puente, una es lxcbr0 que pertenece a LXC y la otra llamada docker0 que pertenece a docker, ambas con si id de puente pero sin ninguna interfaz enlazada al puente. Ya que no tenemos interfaces fisicas conectadas a ella.
