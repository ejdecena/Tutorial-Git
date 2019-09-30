<div align = "center">
    <img src = "imagenes/logo_git.png" width = "70" height = "70" />
</div>

<a name = "cabecera"></a>

# Flujo de trabajo local.

Los archivos en un repositorio local *Git* pasan por 3 fases diferentes:

1. **_Working Directory_** (Directorio de Trabajo).
2. **_Staging Área_** (Área de Preparación o *Index*).
3. **_Git Directory_** (Directorio Git o *HEAD*).

La siguiente figura muestra el esquema de flujo de trabajo local de *Git*:

<p align = "center"><img src = "imagenes/git_flujo_trabajo.png"/></p>

## Fase 1: *Working Directory*.

En esta fase podemos hacer cualquier cambio en los archivos sin afectar nuestro repositorio (*Git Directory*). En cuanto modificamos algo en nuestro código, éste tendrá status de *modificado*. Si ejecutamos el comando `git status` nos mostrará qué archivos han sido modificados (creados o eliminados).

Una vez que hemos hecho los cambios necesarios, pasamos nuestros archivos al *Staging Area* (*Index*) con el comando `git add [archivos]`. Si existen más archivos modificados que queramos pasar podemos listarlos con `git add archivo1.py archivo2.py ...`, o también con el comando `git add .` agregamos **todos** los archivos modificados del *Working Directory* al *Staging Area*.

Cuando se pasan los archivos del *Working Directory* al *Staging Area*, se cambia el estado del código de *modificado* a *preparado*. Para **deshacer** los cambios de **un archivo** en el *Working Directory* con el **último** *commit*, debe usarse el comando `git checkout -- [archivo]`. Los archivos que estén en el *Staging Area* no serán modificados. Para **deshacer todos** los cambios en el *Working Directory* por un *commit* en particular, debemos usar el comando `git checkout [id_commit]`. El `id_commit` podemos obtenerlo con el comando `git log --oneline`.

## Fase 2: *Staging Area* (*Index*).

Para pasar nuestro código del *Staging Area* al *Git Directory* lo hacemos con el comando `git commit -m "[descripción del commit]"`. Hay distintas modalidades para el comando `git commit`que pueden leerse [**aquí**](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Guardando-cambios-en-el-Repositorio). Cuando hacemos el `commit` el código pasa del estado *preparado* a *confirmado*. Para **devolver** **un archivo** del *Staging Área* al *Working Directory* debe ejecutarse `git reset HEAD [archivo]`. Para devolver **todos** los cambios del *Staging Area* al *Working Directory* debemos ejecutar `git reset --hard`.

## Fase 3: *Git Directory* (*HEAD*).

Una vez que el código esta *confirmado* ya está listo para actualizarse en un servidor remoto de *Git* (*GitHub*, *GitLab*, *Bitbucket*, etc.) como veremos más adelante.

## Ignorar archivos.

A veces será deseable que *Git* no añada algunos archivos o directorios al *Working Directory*, o que simplemente estos archivos o directorios no aparezcan como no rastreados. Este suele ser el caso de archivos generados automáticamente o archivos de backup, etc. En estos casos, puedes crear un archivo llamado `.gitignore` que liste los archivos o patrones de nombres de archivos para evitar que estos sean tomados en cuenta por *Git*. Podemos encontrar varios ejemplos del archivo `.gitignore` [**aquí**](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Guardando-cambios-en-el-Repositorio).

En general, el **flujo de trabajo local** básico en *Git* podríamos resumirlo de la siguiente manera:

1. Modificamos una serie de archivos en el *Working Directory*.
2. Preparamos los archivos añadiéndolos al *Staging Area* con `git add`.
3. Confirmamos los cambios con `git commit`, pasando así los archivos al *Git Directory*, creando una copia instantánea y permanente en nuestro directorio de *Git*.

En algunos casos la Fase 2, pasar los archivos al *Staging Area*, puede **omitirse** del *flujo de trabajo*, de tal manera que podemos pasar los archivos **directamente** del *Working Directory* al *Git Directory* añadiendo la opción `-a` al comando `git commit`.

## Ejemplos de flujo de trabajo local.

1. Agrega el archivo del *Working Directory* al *Staging Area* y luego al *Git Directory* (ruta completa):
```bash
$ git add archivo1.py
$ git commit -m "Corrección de error."
```
2. Agrega los archivos del *Working Directory* al *Staging Area* y luego al *Git Directory* (ruta completa):
```bash
$ git add archivo1.py archivo2.py archivo3.py
$ git commit -m "Agregando nueva función."
```
3. Agrega **todos** los cambios del *Working Directory* al *Staging Area* y luego al *Git Directory* (ruta completa):
```bash
$ git add .
$ git commit -m "Se refactorizó las clases no asociadas."
```
4. Agrega todos los cambios del *Working Directory* **directamente** al *Git Directory* (se omite la Fase 2, pero ruta completa):
```bash
$ git commit -am "Cambio de formatos."
```
5. Agrega los `archivo1.py` y `archivo2.py` del *Working Directory* al *Git Directory*, luego se arrepiente y devuelve el archivo1.py al *Working Area* para finalmente pasar solo el archivo2.py al *Git Directory* (ruta incompleta):
```bash
$ git add archivo1.py archivo2.py
$ git reset HEAD archivo1.py
$ git commit -m "Corrección del error en el archivo2.py"
```
6. Igual que el ejemplo anterior, luego del *commit* modifica el `archivo2.py`, se arrepiente de los cambios y lo restituye con la versión del repositorio:
```bash
$ git add archivo1.py archivo2.py
$ git reset HEAD archivo1.py
$ git commit -m "Corrección del error en el archivo2.py"
# luego modifica el archivo2.py en el *Working Directory*
$ git checkout -- archivo2.py
```
Como podemos notar, en el *flujo de trabajo* local básico solo manejamos 4 comandos:
1. `git add [archivos|.]` para pasar los cambios del *Working Directory* al *Staging Area*.
2. `git commit [-a|-m|"mensaje"]` para pasar los cambios del *Staging Area* al *Git Directory*.
3. `git reset [HEAD archivo |--hard]` para **retroceder** y pasar los cambios del *Staging Area* al *Working Directory*.
4. `git checkout [-- archivo|commit_id]` para **retroceder** y pasar los cambios del *Git Directory* al *Working Directory*.

<a href = "README.md#indice">[IR AL ÍNDICE]</a>