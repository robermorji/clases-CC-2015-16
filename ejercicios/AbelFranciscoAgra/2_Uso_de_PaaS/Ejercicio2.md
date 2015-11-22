#Ejercicio 2

Crear una aplicaci—n en _OpenShift_ y dentro de ella instalar _WordPress_. 

###Pasos realizados para la resoluci—n del ejercicio:

1. Se selecciona la opci—n de _Crear Aplicaci—n_ (si es la primera aplicaci—n, existe una opci—n directa llamada _Crear tu Primera Aplicaci—n Ahora_).

2. Seleccionar el tipo de aplicaci—n a crear:

 - Cuenta con una amplia lista de tipos de aplicaciones _web_ (y un buscador para las mismas). 
 
 - Los tipos de aplicaciones se encuentran agrupados por lenguajes de programaci—n (_Java_, _Python_, _Ruby_, etc.) o _Frameworks_ de desarrollo o integraci—n (_Jenkins_, _Drupal_, _WordPress_, entre otros).
 
 - Se selecciona, bajo el grupo "Aplicaci—n Instant‡nea" (_Instant App_), la opci—n de _WordPress 4_.
 
3. Configurar la aplicaci—n a crear:

 - Seleccionar la _URL_ desde la que se podr‡ acceder a la aplicaci—n. Se debe indicar un nombre de aplicaci—n y un nombre de dominio (utilizado para todas las aplicaciones de la cuenta). La _URL_ pœblica es de la forma https://< nombre_aplicacion >-< nombre_dominio >.rhcloud.com
 
 - Se indica el repositorio de _GitHub_ desde el cual se inicializar‡n los archivos por defecto de la aplicaci—n (dependiendo del tipo y lenguaje seleccionado). _Openshift_ cuenta con repositorios de inicializaci—n/ejemplos de cada tipo de aplicaci—n posible.

 - Se indica el contenedor en el cual se ejecutar‡ la aplicaci—n (llamados _gears_), el cual define la cantidad de recursos disponibles. Para cuentas gratuitas solo se puede seleccionar un contenedor b‡sico (_small gear_).
 
 - Se puede seleccionar la regi—n geogr‡fica en la que se desea desplegar la aplicaci—n (Estados Unidos, Europa, etc.). Las cuentas gratuitas (_small gears_) solo pueden desplegar sus aplicaciones en la regi—n Norteamericana (US).
 
4. Se puede iniciar la edici—n del c—digo de la aplicaci—n directamente o finalizar con el despliegue b‡sico (en este caso, se utiliza la œltima opci—n).

5. Finalmente, se especifica un resumen de la instalaci—n y despliegue de la aplicaci—n _web_, as’ como algunos datos adicionales de configuraci—n para otros elementos instalados. En este caso, motor de base de datos incluido (_MySQL 5.5_) y lenguaje de programaci—n (_PHP 5.4_).

6. La aplicaci—n puede ser accedida mediante un navegador _web_ en la _URL_ especificada durante el paso 3. Para el presente ejercicio, la direcci—n es: [https://example-jfrancisco.rhcloud.com](https://example-jfrancisco.rhcloud.com)

7. Es importante destacar que para acceder remotamente al c—digo de la aplicaci—n (y hacer/subir cambios sobre el mismo), se debe incluir una clave SSH pœblica, para que los servidores de _Openshift_ puedan validar los accesos remotos al c—digo fuente de la aplicaci—n.