# Trabajo Practico N° 8

- [Trabajo Practico N° 8](#trabajo-practico-n-8)
  - [Ejercicio 1](#ejercicio-1)
  - [Ejercicio 2](#ejercicio-2)
  - [Ejercicio 3](#ejercicio-3)
  - [Ejercicio 4](#ejercicio-4)

## Ejercicio 1

__ TODO __

## Ejercicio 2

El job llamado "build" (mismo que utiliza como "runner" `ubuntu-latest`) consta de 3 pasos:
- Utiliza la action ` actions/checkout@v2` que permite que el job acceda al repo
- Instalamos JDK con maven
- Buildeamos y corremos el programa con maven

![](img/CI_done.png)

**Nota**: El [codigo del script](https://github.com/MateoCetti/isw-3-spring-boot/blob/main/.github/workflows/maven.yml) de github actions se puede encontrar en el directorio `./git/workflows` del repositorio.

## Ejercicio 3

Creamos el [script](https://github.com/MateoCetti/isw-3-spring-boot/blob/main/.github/workflows/docker-publish.yml), establecemos los secretos y corremos el job.

![](img/secrets.png)

![](img/CI_done.png)

Y como podemos ver, la nueva imagen se subio a docker hub exitosamente:

![](img/hub.png)

## Ejercicio 4