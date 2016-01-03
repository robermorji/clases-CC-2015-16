# Ejercicio 4
## 1. Instalar `lxc-webpanel` y usarlo para arrancar, parar y visualizar las máquinas virtuales que se tengan instaladas.

Para instalar `lxc-webpanel` nos basta con introducir la siguiente línea:

```
wget https://lxc-webpanel.github.io/tools/install.sh -O - | sudo bash
```

Una vez descargado e instalado solo tendremos que acceder a la dirección [http://localhost:5000/](http://localhost:5000/) con el nombre de usuario y contraseña **admin**.

## 2. Desde el panel restringir los recursos que pueden usar: CPU shares, CPUs que se pueden usar (en sistemas multinúcleo) o cantidad de memoria.
