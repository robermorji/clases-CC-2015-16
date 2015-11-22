#Ejercicio 6

Hacer alguna modificaci—n a la aplicaci—n en _node.js_ para _Heroku_, sin olvidar a–adir los tests para la nueva funcionalidad, y configurar el despliegue autom‡tico a _Heroku_ usando _Snap CI_.
 
###Pasos realizados para la resoluci—n del ejercicio:

1. Se incluyen en la librer’a de calificaci—n de empresas, dos (2) nuevas funcionalidades:

 - **_crearAlumno_:** permite registrar un nuevo estudiante (usuario) que puede realizar valoraciones de empresas
 - **_modificarCalificacion_:** permite actualizar o editar una valoraci—n ya definida a una empresa
 
La descripci—n e implementaci—n de estas funcionalidades pueden observarse en el archivo [libCalificacionempresa.js](https://github.com/jfrancisco4490/calificacionEmpresa_2/blob/master/lib/libCalificacionempresa.js).

2. Se incluyen dos (2) nuevas rutas en la aplicaci—n, para soportar solicitudes _HTTP_ que utilicen y apliquen las operaciones definidas en el punto anterior.

 - `PUT /alumno/<usr>/<nombre>/<apellido>/<extra>` que define una solicitud de registro de nuevo alumno (enviando todos los par‡metros asociados al mismo)
 - `POST /calificacion/<empresa>/<alumno>/<valor>` que especifica una operaci—n de actualizaci—n del valor de una calificaci—n ya realizada a una empresa 

Las nuevas rutas se ubican en el archivo [index.js](https://github.com/jfrancisco4490/calificacionEmpresa_2/blob/master/routes/index.js).

3. Se definen dos (2) nuevos _tests_ para las funcionalidades, verificando el registro de un nuevo alumno y la actualizaci—n de una calificaci—n de forma exitosa.

Para el registro de un nuevo alumno:

```
	describe("PUT Alumno", function() {
		it('Deber’a Crear Nuevo Alumno', function (done) {
			request(app)
			.put('/alumno/Usr4/Nombre4/Apellidos4/Extra4')
			.expect(200,done)
			.end(function(err, res){
      			if (err) {
            		return done(err);
          		}
      			res.text.should.match(/Finalizada con exito/);
      			done();
      		});
		});
	});
```

Para la actualizaci—n de una calificaci—n:

```
	describe("POST Calificaci—n", function() {
		it('Deber’a Modificar Calificaci—n', function (done) {
			request(app)
			.post('/calificacion/Emp4/Usr1/1')
			.expect(200,done)
			.end(function(err, res){
      			if (err) {
            		return done(err);
          		}
      			res.text.should.match(/Finalizada con exito/);
      			done();
      		});
		});
	});
```

Los nuevos _tests_ se encuentran especificados en el archivo [test.js](https://github.com/jfrancisco4490/calificacionEmpresa_2/blob/master/test/test.js).

4. Se realiza el registro en el servicio de integraci—n continua de _Snap CI_, asociando una cuenta de _GitHub_.

5. Se incluye el repositorio correspondiente con la aplicaci—n de calificaci—n de empresas en _Snap CI_, lo cual ejecuta autom‡ticamente el primer proceso de integraci—n continua (_build_).

6. Se configura la integraci—n continua en _Snap CI_ para que ejecute los _tests_ (_mocha_) en cada nueva actualizaci—n del c—digo en el repositorio.

7. Para integrar _Snap CI_ con _Heroku_ de forma autom‡tica, se define un nuevo paso (_stage_) en la secuencia de la integraci—n continua:

 - En la configuraci—n del nuevo _stage_ en _Snap CI_, se indica que se va a realizar un despliegue b‡sico en _Heroku_
 - Se indica la cuenta de _Heroku_ con la que se van a realizar los despliegues
 - Se puede utilizar en una aplicaci—n ya creada en _Heroku_, o definir una nueva. En este caso, se define una nueva aplicaci—n.

8. Al guardar la configuraci—n del nuevo paso, _Snap CI_ inicia de forma autom‡tica una nueva ejecuci—n de la integraci—n continua, que ahora incluye el despliegue de la aplicaci—n en _Heroku_.

Ahora, cada vez que se ejecute una actualizaci—n del c—digo en _GitHub_ (_push_), se activa la integraci—n continua en _Snap CI_, que culmina en el despliegue autom‡tico de la aplicaci—n en _Heroku_.

El estado actual de la ejecuci—n de la integraci—n continua sobre la aplicaci—n puede observarse en la medalla (_badge_) de _Snap CI_, ubicado en la p‡gina principal del repositorio.