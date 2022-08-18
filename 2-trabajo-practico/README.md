# Trabajo practico N°2

- [Trabajo practico N°2](#trabajo-practico-n2)
  - [Ejercicio 1](#ejercicio-1)
  - [Ejercicio 2](#ejercicio-2)
  - [Ejercicio 3](#ejercicio-3)
  - [Ejercicio 4](#ejercicio-4)
  - [Ejercicio 5](#ejercicio-5)
  - [Ejercicio 6](#ejercicio-6)
  - [Ejercicio 7](#ejercicio-7)
  - [Ejercicio 8](#ejercicio-8)
  - [Ejercicio 9](#ejercicio-9)
  - [Ejercicio 10](#ejercicio-10)

## Ejercicio 1

**Version** de docker instalada:

![](img/docker_version.png)

## Ejercicio 2

**Cuenta creada** y familiarizandome con **docker-hub**:

![](img/docker_hub.png)

## Ejercicio 3

![](img/busybox_dowload.png)

![](img/docker_images.png)

## Ejercicio 4

No se obtuvo nada porque el comando no se ejecuto con las **flags**:
* **-d**: detached mdoe
* **-it**: interactive mode

O algun otro modo, por lo que el contenedor (en este caso busybox) se **ejecuta** exitosamente y posteriormente **termina** su ejecución sin emitir ningun tipo de **log** en consola.

## Ejercicio 5

Creamos el contenedor de manera **interactiva** y ejecutamos los comandos.

![](img/inside_container.png)

## Ejercicio 6

Vemos y **borramos** los contenedores

![](img/containers_deleted.png)

## Ejercicio 7

Ejecutando el comando

![](img/command_creating_volume.png)

Creando el fichero dentro del directorio especificado (dentro del contenedor)

![](img/creating_file.png)

Verificando que el archivo se creo en el volumen

![](img/file_created_in_volume.png)

## Ejercicio 8

Ejecutamos el comando con la flag -d para que dicho contenedor se siga ejecutando en background.

![](img/nyan_cat_container.png)

Borramos el contenedor

![](img/deleting_container.png)

Accedemos mediante un navegador al localhost en el puerto 80 

![](img/nyan_cat_uwu.png)

## Ejercicio 9 

Creamos el contenedor psql y el volumen (descargamos la imagen ya que no la tengo localmente)

![](img/creating_psql_container_and_volume.png)

Nos metemos dentro del psql del contenedor y ejecutamos los comandos SQL.

![](img/sql_execution.png)

Por ultimo, interactuamos con la DB utilizando dbeaver.

![](img/dbeaver_interacting.png)

Con el comando `docker run` descargamos la imagen de psql del repositorio imagen en docker-hub a nuestro equipo local, creamos un contenedor con dicha imagen y los parametros especificados en las flags escritas al correr dicho comando y levanta dicho contenedor.

En cambio con `docker exec` ejecutamos un comando (en este caso `psql -h localhost -U postgres`) en un contenedor que ya esta corriendo.

## Ejercicio 10

Es este documento.