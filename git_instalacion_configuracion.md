<div align = "center">
    <img src = "imagenes/logo_git.png" width = "70" height = "70" />
</div>

# ¿Qué es GIT?

[GIT](https://git-scm.com/book/es/v2) es un [sistema de control de versiones](https://es.wikipedia.org/wiki/Control_de_versiones) que nos permite:

1. Trabajar en equipo de forma remota, simple y óptima mientras desarrollamos software.

2. Controlar y hacer seguimiento de todos los cambios en el código fuente, pudiendo volver atrás en el tiempo y abrir diferentes ramas de desarrollo.

<a href = "#indice">[IR AL ÍNDICE]</a>

<a name = "instalacion"></a>

## Instalación y configuración.

Para instalar *Git* en un sistema operativo *Linux* con paquetería *apt* (*Debian*, *Ubuntu*, *Linux Mint*, etc) basta con ejecutar el siguiente comando desde la terminal:

```bash
$ sudo apt-get install git
```
Para la instalación en otros sistemas operativos se puede consultar [**aquí**](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Instalación-de-Git).

Luego de la instalación deberán establecerse las **variables de configuración** de *Git* para personalizar el entorno de trabajo. Es necesario hacer esta configuración **solamente una vez** en el computador, ya que estas variables se mantendrán entre actualizaciones. También se pueden cambiar estas variables en cualquier momento, volviendo a ejecutar los comandos correspondientes.

*Git* trae una herramienta llamada `git config`, que nos permite establecer y obtener las variables de configuración las cuales controlan el aspecto y funcionamiento de *Git.*

## Estableciendo la identidad del usuario.

Lo primero que debe hacerse luego de instalar *Git* es **establecer la identidad del usuario**. Esto es importante porque los *commits* de *Git* usan esta información de manera automática en todos los *commits* que se hagan en el repositorio.

Las principales variables de configuración son el **nombre de usuario** y el **email**. Para establecer estas variables hay que ejecutar en la terminal las siguientes instrucciones:

```bash 
$ git config --global user.name "Pedro Pérez"
$ git config --global user.email pedro.perez@gmail.com
```
Para comprobar la configuración se puede usar el comando `git config --list`, el cual mostrará los cambios recientes además de las variables de configuración adicionales:

```bash
$ git config --list
user.name=Pedro Pérez
user.email=pedro.perez@gmail.com
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
```
Opcionalmente también pueden establecerse el **editor** por defecto a usar para los *commits*, y establecer mostrar sólo una línea por cada `commit` en la traza:
```bash
$ git config --global core.editor [nombre-editor]
$ git config --global format.pretty oneline
```

## Obteniendo ayuda.

Para obtener ayuda sobre cualquier comando de *Git* podemos usar:
```bash
$ git help [comando]
```
Sin embargo, existen dos formas adicionales para obtener ayuda de *Git* que se pueden consultar [**aquí**](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-¿Cómo-obtener-ayuda%3F)

<a href = "#README.md">[IR AL ÍNDICE]</a>