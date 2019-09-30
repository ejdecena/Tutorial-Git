<div align = "center">
    <img src = "imagenes/logo_git.png" width = "70" height = "70" />
</div>

<a name = "cabecera"></a>

# Herramientas adicionales Git.

Los 4 comandos de la sección anterior son básicos para el *flujo de trabajo* local y de algún modo son suficientes, pero existen 3 comandos adicionales que **complementan** las tareas: `git diff`, `git log` y `git tag`.

## Observando las diferencias entre archivos.

Siempre es posible ver los cambios o diferencias de los archivos en las distintas fases, por ejemplo:
* `git diff` muestra las diferencias de los archivos entre el *Working Directory* y *Staging Area*.
* `git diff HEAD` muestra las diferencias de los archivos entre el *Working Directory* y *Git Directory*. 
* `git diff --staged` muestra las diferencias de los archivos entre el *Staging Area* y el *Git Directory*.

El comando `git diff` tiene múltiples opciones que pueden leerse [**aquí**](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Guardando-cambios-en-el-Repositorio).

## Observando la historia de commits.

También siempre es posible ver el *historial* de cambios del repositorio *Git Directory* con el comando `git log`. Este comando tiene múltiples opciones las cuales pueden leerse [**aquí**](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Ver-el-Historial-de-Confirmaciones).

## Añadiendo tags a los commits.

Cuando vemos el historial de los *commits* con `git log` podemos ver algo como esto:
```bash
commit eece07985eec4d1ccad5cd8022e6a806086dcbd2
Author: Edgard Decena <edecena@gmail.com>
Date:   Thu Sep 26 04:37:46 2019 -0400

    Más ejemplos y resumiendo el flujo de trabajo local básico.

commit 81d19320683852a928d35759b7173b098ac1d126
Author: Edgard Decena <edecena@gmail.com>
Date:   Wed Sep 25 23:38:10 2019 -0400

    Correcciones varias.

commit c0961e1ee659f56713e7389fc1e293ff1f68883b
Author: Edgard Decena <edecena@gmail.com>
Date:   Wed Sep 25 23:34:52 2019 -0400

    Agregando subtítulos de diff, log y tag. Arreglos varios.
```
Sin embargo se recomienda crear **etiquetas** (*tags*) para aquellos *commits* que marquen un *hito* o que sean importantes, como por ejemplo una **versión** del software. Para crear las etiquetas se usa el comando `git tag`. Veamos el siguiente ejemplo:
```bash
$ git tag 1.0.0 eece07985e
```
Agrega la etiqueta `1.0.0` al primer *commit*, el marcado con el hash `eece07985eec4d1ccad5cd8022e6a806086dcbd2`. Nótese que en el ejemplo solo usamos los 10 primeros caracteres del hash. El comando `git tag` tiene múltiples opciones las cuales pueden leerse [**aquí**](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Etiquetado). 

<a href = "README.md#indice">[IR AL ÍNDICE]</a>