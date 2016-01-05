# Ejercicio
## Crear a partir del contenedor anterior una imagen persistente con commit.
Para crear una imagen persistente a partir de un contenedor necesitaremos mínimo conocer su ID largo, para eso añadimos al comando de lista los contenedores de Docker la opción `-notrunc`. Con este ID además podemos **"inspeccionar"** (opción `inspect`) dichos contenedores para obtener diversa información, como el nombre del host, la imagen cargada, si el contenedor está en funcionaniento o la dirección IP.

```
docker ps -notrunc
docker inspect CONTAINER_ID
```

Así que simplemente usando la opción **commit**, el ID largo de nuestro contenedor y una etiqueta que usaremos para identificarlo, crearemos una imagen persistente con el estado actual de nuestro contenedor. La imagen aparecerá con el nombre de etiqueta que le hayamos dado en el listado con el resto de imágenes.

```
docker commit CONTAINER_ID nginx
docker images
```

Tener una imagen mínima de un sistema operativo con un servidor como **nginx** instalado es interesante, porque con pocos recursos podemos tener un servidor que podemos arrancar independientemente en cualquier momento, simplemente deberemos conocer su dirección IP.

Y podremos acceder desde cualquier navegador que tenga acceso a esa dirección IP.
