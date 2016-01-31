**Destruir toda la configuración creada anteriormente**

Destruimos el entorno local creado :

```sudo juju destroy-environment local```


**Volver a crear la máquina anterior y añadirle mediawiki y una relación entre ellos.**

Repetimos los pasos anteriores. Usamos el comando ```juju debootstrap``` para crear los contenedores. A continuación instalamos mysql y la mediawiki.

```
juju deploy mysql
juju deploy mediawiki
```

Y creamos la relación entre mysql y mediawiki para indicarle a la wiki la base de datos que usará.

```juju add-relation mediawiki:db mysql```

Y finalmente podemos lanzar el servicio para poder ser usado.

```juju expose mediawiki```
