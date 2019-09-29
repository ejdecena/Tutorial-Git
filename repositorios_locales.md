<div align = "center">
    <img src = "imagenes/logo_git.png" width = "70" height = "70" />
</div>

# Creando repositorios locales.

Con *Git*  se pueden crear nuevos repositorios básicamente de dos maneras:

1. Convirtiendo una carpeta (directorio) en repositorio ejecutando la instrucción `git init` dentro del directorio; o también, si el directorio no existe, puede crearse con el comando `git init [nuevo-repositorio]` que automáticamente creará el directorio con el nombre `nuevo-repositorio`.

2. La otra forma de crear un nuevo repositorio es *clonándolo* desde otra ubicación con el comando `git clone [nombre-repositorio] [dirección URL/URI]`. Por defecto *Git* establece [nombre-repositorio] a *origin* si no se especifica. Por ejemplo, para clonar este repositorio localmente basta con hacer `git clone https://github.com/ejdecena/tutorial_git.git`, el cual creará un directorio local con el nombre de *tutorial_git*. Si se quiere clonar el repositorio a un directorio con otro nombre distinto al original, se puede especificar un tercer parámetro al comando `git clone [nombre-repositorio] [dirección URL/URI] [nombre-directorio]`. Por ejemplo el comando `git clone https://github.com/ejdecena/tutorial_git.git mi_repo` creará el directorio `mi_repo` con el repositorio clonado.

<a href = "README.md#indice">[IR AL ÍNDICE]</a>