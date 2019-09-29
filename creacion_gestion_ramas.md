<div align = "center">
    <img src = "imagenes/logo_git.png" width = "70" height = "70" />
</div>

# Creación y gestión de ramas.

El manejo de *ramas* es muy sencillo en *Git* y básicamente se reduce a 3 comandos:

* `git branch [nombre-rama]` **crea** la rama `nombre-rama`. Si se omite el parámetro `nombre-rama` el comando muestra todas las ramas del repositorio.
* `git checkout [nombre-rama]` nos **cambia** a la rama `nombre-rama`.
* `git checkout -b [nombre-rama]` **crea** la rama `nombre-rama` y nos **cambia** de una vez a la rama.
* `git checkout -d [nombre-rama]` **elimina** la rama [nombre-rama].
* `git merge [nombre-rama]` **combina** la rama activa con [nombre-rama].

Siempre vamos a tener una rama `master` que será la rama principal. Supongamos que creamos la rama `desarrollo` para hacer pruebas:
```bash
$ git checkout -b desarrollo
```
En `desarrollo` creamos nuevos archivos y modificamos archivos ya existentes. Para **unir** (*merge*) estos cambios a la rama `master` primero tenemos que hacer *commit* en `desarrollo` y luego **cambiarnos** a la rama `master` así:
```bash
$ git commit -am "Agregando cambios finales a desarrollo."
$ git checkout master
```
Estando ya en la rama `master` podemos **unir** (*merge*) los cambios en la rama `desarrollo` así:
```bash
$ git merge desarrollo
```
Luego si todo fue OK podemos eliminar la rama `desarrollo` así:
```bash
$ git checkout -d desarrollo
```
Cuando se hace un *merge* es posible que hayan conflictos al tratar de cambiar archivos que ya tengan otros cambios, estos conflictos deberán **resolverse manualmente** antes de intentar un nuevo *merge*. Para obtener más información sobre el manejo de las ramas podemos ir [**aquí**](https://git-scm.com/book/es/v2/Ramificaciones-en-Git-¿Qué-es-una-rama%3F).

<a href = "README.md#indice">[IR AL ÍNDICE]</a>