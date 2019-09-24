# Tutorial GIT.

*Tutorial GIT* es una guía básica para comprender y usar las principales funcionalidades del sistema de control de versiones *Git*.

<img src="https://img.shields.io/badge/License-MIT-green" /> <img src="https://img.shields.io/badge/Markdown-1.0.1%20-blue" />


## Desarrolladores.

* [Ing. Edgard Decena.](mailto:edecena@gmail.com)
* [Ing. Luís Acevedo.](mailto:laar19@protonmail.com)


## ¿Qué es GIT?

[GIT](https://git-scm.com/book/es/v2) es un [sistema de control de versiones](https://es.wikipedia.org/wiki/Control_de_versiones) que nos va a permitir:

1. Trabajar en equipo de una manera simple y óptima cuando estemos desarrollando software.

2. Controlar todos los cambios en el código fuente, pudiendo volver atrás en el tiempo y abrir diferentes ramas de desarrollo.


## Instalación y configuración de GIT.

Para instalar *Git* en un sistema operativo *Linux* con paquetería *apt* (*Debian*, *Ubuntu*, etc) basta con ejecutar la siguiente instrucción desde la terminal:

```bash
sudo apt-get install git
```
Para la instalación en otros sistemas operativos se puede consultar [**aquí**](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Instalación-de-Git).

Luego de la instalación deberán hacerse algunas cosas adicionales para personalizar el entorno de *Git*. Es necesario hacer estas cosas **solamente una vez** en el computador, ya que estas se mantendrán entre actualizaciones. También se puede cambiarlas en cualquier momento, volviendo a ejecutar los comandos correspondientes.

*Git* trae una herramienta llamada `git config`, que nos permite establecer y obtener variables de configuración; dichas variables de configuración controlan el aspecto y funcionamiento de *Git.*

### Estableciendo la identidad del usuario.

Lo primero que deberá hacerse luego de instalar *Git* es establecer la **identidad** del usuario. Esto es importante porque los *commits* de *Git* usan esta información que es introducida de manera automática en todos los commits que se hagan.

Las principales variables de configuración son el **nombre de usuario** y el **email**. Para establecerlos hay que ejecutar en el terminal las siguientes instrucciones:

```bash 
git config --global user.name "Pedro Pérez"
git config --global user.email pedro.perez@gmail.com
```
Para comprobar la configuración se puede usar el comando `git config --list`, el cual mostrará los cambios recientes además de las variables de configuración adicionales:

```bash
git config --list
user.name=Pedro Pérez
user.email=pedro.perez@gmail.com
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
```

### Obteniendo ayuda de GIT.

Para obtener ayuda de cualquier comando de *Git* el comando más usado es:
```bash
git help [comando]
```
Sin embargo, existen dos formas adicionales de obtener ayuda de *Git* que se pueden consultar [**aquí**](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-¿Cómo-obtener-ayuda%3F)


## Crear nuevos repositorios en GIT.

Con *Git*  se puede crear un nuevo repositorio básicamente de dos maneras:

1. Convirtiendo una carpeta (directorio) en repositorio ejecutando la instrucción `git init` dentro del directorio; o también, si el directorio no existe, puede crearse con el comando `git init [nuevo_repositorio]` que automáticamente creará el nuevo_repositorio.

2. La otra forma de crear un nuevo repositorio es *clonándolo* desde otra ubicación con el comando `git clone [nombre_repositorio] [dirección URL/URI]`. Por defecto *Git* establece [nombre_repositorio] a *origin* si no se especifica. Por ejemplo, para clonar este repositorio localmente basta con hacer `git clone https://github.com/ejdecena/tutorial_git.git`. Si se quiere clonar el repositorio a un directorio con otro nombre distinto al original, se puede especificar un tercer parámetro al comando `git clone [nombre_repositorio] [dirección URL/URI] [nombre_directorio]`. Por ejemplo el comando `git clone https://github.com/ejdecena/tutorial_git.git mi_repo` creará una carpera `mi_repo` con el repositorio clonado.


## Flujo de trabajo local.

## Creación y gestión de ramas.

## Participando en proyectos de GitHub.