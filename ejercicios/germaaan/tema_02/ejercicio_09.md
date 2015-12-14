# Ejercicio 9
## Realizar un pequeño programa, en el lenguaje elegido y sobre la base de datos "tradicional" elegida (PostgreSQL o cualquier otro online) que realice el ciclo básico de una base de datos. Puede ser la aplicación de calificación de empresas realizada anteriormente.

El programa que he realizado para este ejercicio se puede encontrar en [este repositorio](https://github.com/germaaan/calificaEmpPost). Antes de ejecutar el programa es importante exportar la varible de entorno `DATABASE_URL` con la información para conectar a base de datos PostgreSQL, pudiendo esta estar en nuestra máquina local o como en este caso en la nube mediante la plataforma [ElephantSQL](http://www.elephantsql.com/).

```
export DATABASE_URL=postgres://USUARIO:CONTRASEÑA@URL:PUERTO/BASEDATOS
```

- Ejecutar la consulta de selección `SELECT * FROM calificaciones` mediante la dirección [http://localhost:3000/](http://localhost:3000/):

![eje09_img01.png](https://dl.dropboxusercontent.com/s/0n5gl61siohj2cu/eje09_img01.png)

- Ejecutar la consulta de inserción `INSERT INTO calificaciones(empresa, alumno, calificacion) VALUES('meh', 'germaaan', '0')` mediante la dirección [http://localhost:3000/insert/meh/germaaan/0](http://localhost:3000/insert/meh/germaaan/0):

![eje09_img02.png](https://dl.dropboxusercontent.com/s/n991eoucpfoaguj/eje09_img02.png)

- Ejecutar la consulta de actualización `UPDATE calificaciones SET calificacion=100 WHERE id=43` mediante la dirección [http://localhost:3000/update/43/100](http://localhost:3000/update/43/100):

![eje09_img03.png](https://dl.dropboxusercontent.com/s/shvc5knre94qe0i/eje09_img03.png)

- Ejecutar la consulta de eliminación `DELETE FROM calificaciones WHERE id=43` mediante la dirección [http://localhost:3000/delete/43](http://localhost:3000/delete/43):

![eje09_img04.png](https://dl.dropboxusercontent.com/s/194ophuqbxuc0tw/eje09_img04.png)
