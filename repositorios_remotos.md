<div align = "center">
    <img src = "imagenes/logo_git.png" width = "70" height = "70" />
</div>

<a name = "cabecera"></a>

# Agregar y gestionar repositorios remotos.

Hasta ahora hemos trabajado en forma local con nuestro repositorio; sin embargo, es deseable que podamos compartir nuestro código con otros colaboradores en forma remota. Para ello debemos *linkear* nuestro repositorio local con uno o varios repositorios remotos de la siguiente manera:
```bash
$ git remote add [nombre-repositorio] [URL/URI]
```
Nuestro repositorio local puede tener establecidos **varios** repositorios remotos, esto en el caso que estemos trabajando con varios colaboradores. Esta flexibilidad es posible porque *Git* es un sistema de [**control de versiones distribuído**](https://es.wikipedia.org/wiki/Control_de_versiones_distribuido); es decir, que cada colaborador (*Nodo*) tiene una misma **copia completa** de nuestro repositorio. Para ver una lista de los repositorios remotos *linkeados* a nuestro repositorio local basta con ejecutar el siguiente comando: 
```bash
$ git remote -v
```
Si previamente hemos *clonado* un repositorio remoto, automáticamente este repositorio de donde clonamos **queda establecido**, y no es necesario ejecutar el `git remote add`.

## Eliminar y renombrar remotos.

Para **eliminar** un repositorio remoto *linkeado* a nuestro repositorio local podemos ejecutar `git remote rm [nombre-remoto]`. Para **cambiar el nombre** de la referencia de un remoto podemos ejecutar `git remote rename [nombre-actual] [nuevo-nombre]`.

## Inspeccionando un remoto.

Para ver información sobre un repositorio remoto en particular, podemos ejecutar el comando `git remote show [nombre-remoto]`. Si ejecutamos el comando con un nombre en particular, como `origin` verás algo como lo siguiente:
```bash
* remote origin
  Fetch URL: https://github.com/ejdecena/tutorial_git.git
  Push  URL: https://github.com/ejdecena/tutorial_git.git
  HEAD branch: master
  Remote branch:
    master tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local ref configured for 'git push':
    master pushes to master (up to date)
```

## Actualizando el repositorio remoto.

Para actualizar el repositorio remoto a partir de nuestro repositorio local, ejecutamos el comando `git push` de la siguiente forma:
```bash
$ git push [nombre-remoto] [rama-remoto]
```
Un ejemplo típico es:
```bash
$ git push origin master
```
Si queremos **fijar** o establecer un *push* por defecto, por ejemplo el `origin master` del ejemplo anterior, usamos el parámetro `-u` de la forma:
```bash
$ git push -u origin master
```
Así, en el próximo *push* simplemente ejecutamos:
```bash
$ git push
```
y *Git* entenderá que deberá hacer el *push* al `origin master`.

## Actualizando el repositorio local.

Has **dos** maneras de actualizar el repositorio local con los datos del repositorio remoto, a través de los comandos `git pull` y `git fetch`.

* El comando `git pull [nombre-remoto] [rama-remota]` **automáticamente combinará** (hará un *merge*) de la [rama-remota] con la rama local en la que nos encontremos, por ejemplo si localmente estamos en la rama `master` hará un *merge* con la rama `master` del repositorio remoto.

* El comando `git fetch [nombre-remoto]` solo trae los datos al repositorio local, es decir **no los combina automáticamente con tu trabajo ni modifica el trabajo que llevas hecho**. La **combinación** (*merge*) con tu repositorio local **debes hacerla manualmente** cuando estés listo.

En todo repositorio local existe una **rama oculta** que puedes ver al ejecutar `git branch -a`, esa rama oculta es `origin/master`. Al usar `git fetch` bajas los cambios del repositorio remoto a la rama oculta `origin/master`, luego tendrías que hacer un *merge* para combinarla con tu rama local haciendo `git merge origin/master`.

<a href = "README.md#indice">[IR AL ÍNDICE]</a>