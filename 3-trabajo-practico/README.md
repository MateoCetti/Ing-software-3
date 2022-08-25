# Trabajo practico N° 3

- [Trabajo practico N° 3](#trabajo-practico-n-3)
  - [Ejercicio 1](#ejercicio-1)
  - [Ejercicio 2](#ejercicio-2)
  - [Ejercicio 3](#ejercicio-3)
  - [Ejercicio 4](#ejercicio-4)
  - [Ejercicio 5](#ejercicio-5)

## Ejercicio 1

Por defecto el driver utilizado para crear la network es "bridge" por lo que me saltee la flag `-d`

![](img/network_create.png)

Creamos el contenedor con redis y lo conectamos  a la red "mybridge"

![](img/creating_redis.png)

Creamos una app web que consuma esta db, conectando dicho contenedor a la red "mibridge" (En este caso la app web es una app creada en python con flask). Para ello establecemos como variables de entorno (mediante la flag `-e` el host del redis que como el contenedor se encuentra en la red se puede referenciar como "db" y el puerto)

![](img/creating_flask.png)

![](img/5000.png)

Listamos los contenedores y networks creados

![](img/web_and_db.png)

![](img/networks.png)

Detallamos la info de la red "mybridge"

![](img/mybridge.png)

Los respectivos comandos se encuentran en las caputras de pantalla

## Ejercicio 2

El sistema importa las librerias:

* `os`: para poder leer las variables de entorno del sistema (o contenedor).
* `flask`: para poder crear una aplicación web de manera rapida y simple.
* `redis`: para poder conectarse a una instancia de redis con python.

Luego crea una aplicación de flask, crea una conexión a **redis** mediante las utilidades provistas por las libreria de python `redis` y `os` (esta ultima para obtener las variables de entorno con el host y port de la instancia de redis) y  y establece una variable "global" con el **puerto** que se abrira para **exponer** el servicio.

Luego, haciendo uso de flask, creamos una ruta para el directorio o endpoint "raiz" o index el cual incrementara en uno el contador de hits almacenado en redis, obtendra la cantidad de hits de dicho contador y lo devolvera en un string formateado.

Por ultimo, en el caso en el que el script se corra (y no se importe como modulo) se correra  la aplicación de redis definida anteriormente.

Los parametros -e establecen las variables de entorno necesarias para que la app funcione.

Si eliminamos y volvemos a crear un contenedor web, no sucede nada extraño, es mas, ni se pierden los datos de los hits registrados en redis.

![](img/re_run_web.png)

![](img/2_5000.png)

Sin embargo, cuando borramos el contenedor de redis y recargamos la app web, esta devuelve un error ya que intenta conectarse con la instancia de redis, pero como la borramos, esta es inexistente.

![](img/error.png)

Al levantarlo de nuevo, la app vuelve a funcionar sin problemas (al recargar la pagina), pero el contador de hits se a reiniciado a 0 debido a que los datos se eliminaron cuando eliminamos el contenedor de redis. Para que esto no suceda, deberiamos de crear un volumen y linkearlo al contenedor, de tal manera que los datos persistan en dicho volumen, independientemente de que si el contenedor se borre o no.

Corremos los comandos:

```bash
docker rm -f db
docker rm -f web
docker network rm mybridge
```

y borramos los contenedores y la red.

## Ejercicio 3

![](img/docker-compose.png)

Lo que hizo docker compose fue basicamente realizar todo lo que hicimos en el ejercicio 1 de manera automatizada y solo con escribir un simple script en `.yaml`, ademas de crear un **volumen** para redis.

## Ejercicio 4



## Ejercicio 5