Redis
======================================================================

1. Darse de alta en un servicio Redis en la nube y realizar sobre él las operaciones básicas desde el panel de control.
 + Para instalar Redis, usamos el comando `sudo apt-get install redis-server`

2. Instalar un cliente de línea de órdenes de Redis o una biblioteca cliente REST y realizar desde él las operaciones básicas de creación y lectura de información.
 + Para acceder a redis, usamos el comando `redis-cli`
 + Para escibir un valor dentro de una variable, usamos el comando `set uno 1`
 + Para leer el valor guardado usamos `get uno`

3. Ejecutar ejemplos de cualquier lenguaje de programación sobre la instalación realizada.
Antes de ejecutarlo deberemos exportar una varible de entorno con la dirección de acceso a la base de datos (en este caso estamos usando una instalación local, pero sería igual para una instalación en la nube). Recordar que es necesario instalar las dependencias antes de ejecutarlo.
`Código de Germán Martínez`
```
#!/usr/bin/env node

var redis = require('redis');
var url = require('url');

var redisURL = url.parse(process.env.REDISCLOUD_URL);
console.log(redisURL);
var client = redis.createClient(redisURL.port, redisURL.hostname, {
  no_ready_check: true
});

client.set("prueba", "clave", redis.print);
client.get("prueba", function(err, reply) {
  console.log('Get ');
  if (err) {
    console.log(err);
  } else {
    console.log(reply.toString());
  }
});

client.hset("cosa", "campo1", "hola", redis.print);
client.hset("cosa", "campo2", "mundo", redis.print);
client.hkeys("cosa", function(err, replies) {
  console.log('hkeys');
  replies.forEach(function(reply, i) {
    console.log("    " + i + ": " + reply);
  });
  console.log("End ");
  client.end();
});
```

Para ejecutar el programa:
```
export REDISCLOUD_URL=http://127.0.0.1:6379
npm install redis url
node pruebaRedis
```

Y lo que se produce luego de la ejecución es:
```
Url {
  protocol: 'http:',
  slashes: true,
  auth: null,
  host: '127.0.0.1:6379',
  port: '6379',
  hostname: '127.0.0.1',
  hash: null,
  search: null,
  query: null,
  pathname: '/',
  path: '/',
  href: 'http://127.0.0.1:6379/' }
Reply: OK
Get 
clave
Reply: 1
Reply: 1
hkeys
    0: campo1
    1: campo2
End 
```


1. Se usará para este ejercicio, la aplicación de ejemplo dada por Heroku y un buildpack que utiliza grunt para aplicar tareas sobre los procesos de compilación, revisión de código, etc.
 * `heroku apps:create herokunuevabuildpack --region eu --buildpack https://github.com/mbuchetics/heroku-buildpack-nodejs-grunt.git`

2. Actualizar la variable de entorno NODE-ENV, indicando que el ambiente es de producción:
 * `heroku config:set NODE_ENV=production`

3. Definir un archivo Gruntfile.js con una tarea específica llamada heroku, de la siguiente manera:
 * grunt.registerTask('heroku:development', ['auto_install', 'jshint']); (para ejecutar si el ambiente de despliegue es de desarrollo)
 * grunt.registerTask('heroku:production', ['auto_install', 'concat', 'uglify', 'jshint']); (actividades a ejecutar si el ambiente es de producción)

4. Añadir dependencias de Grunt en el package.json
```
"dependencies": {
  ...
  "grunt": "^0.4.5",
  "grunt-auto-install": "^0.3.0",
  "grunt-contrib-concat": "^0.5.1",
  "grunt-contrib-jshint": "^0.11.3",
  "grunt-contrib-uglify": "^0.10.0",
  ...
}
```

5. Se despliega el repositorio (con el Gruntfile.js) a Heroku:

`git push heroku master`

Para acceder a la app, se puede hacer desde [aquí](http://herokunuevabuildpack.herokuapp.com/)
