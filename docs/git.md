# Git que es

git es un controlador de versiones que mas utlizado en todo el mundo. en otras palabras con git podemos tener un historia de todo el codigo que hemos desarrollado en nuetro sotfware.

existen 2 tipos de repositorio por decirlo se una manera

- **local**: en este los cambios se guardaran solo en el equipo. 
- **online**: este tipo trabaja junto con el local, el cual guarda los cambios locales y permite compartirlo con otros usuarios.
## Que es mejor CLI o GUI

la interfas CLI que es la que veremos aqui es mucho mas potente de lo que sera cualquier etorno GUI ya que por lo general estan bastante limitadas. ademas que desde el CLI siempre sera igual sin importar el sitema operativo que uses.

## Crear repositorio local

para crear un repositorio hay que estar primero dentro
de la capeta con tu terminal de preferencia y ejecutar el siguiente codigo

`git init`

este creara un repositorio local
la evidencia de que funcione es que 
aparesca una carpeta oculta con el nombre *.git*
## Configurar GIT

```zsh
# configuraciones de usuario
git config --global user.name "[nombre]"
git config --global user.email [Correo]
# editor de codigo predeterminado
git config --global core.editor "code --wait"
git config --gobal -e
#linux/mac = input ; windows= true
git config --global core.autocrlf [input/true]

```



## Guardar cambios local

cuando generas un repositorio o haces un 
cambio tienes que guardar esos cambios o archivos nuevos,
para eso tienes que usar el comando `git add [archivo]`
tambien puede ser toda una carpeta, pero si quieres guardar todo
sin importar que sea usa el comando `git add -all` o tambien puedes usar `git add -A`

Una vez creado tienes que comentar el archivo
### borrar cambio guardado
`git restore --staged [archivo]`

### Generar Commit

el commit nos permite anotar los cambios y saber que se hizo en ese archivo
lo recomensable es hacer un comit, para cada archivo subido por add sino agregara a todos bajo el mismo commit

el comando a utilizar es `git commit -m "[Comentario]"` ya esta listo para subir el archivo al repositorio.

## Repositorio Online

Pasa subir archivos al repositorio que pude ser en [GitHub](https://www.github.com/) o [GitLab](https://about.gitlab.com). 


### Conectar Repositorio
usando este comando para conectar tu local al repositorio en [GitHub](https://www.github.com/) o [GitLab](https://about.gitlab.com). 

`git remote add [alias]`

por lo general el nombre del alias es **origin** pero puedes usar cualquier nombre para la conexion.
#### Eliminar Conexion
En caso de que te equivoques o cualquier fallo puedes borrarlo con el comando:

`git remote remove [conexion]`

Ejemplo que el nombre de la conexion sea origin: `git remote remove origin`

### Subir commit al repositorio

`git push [conexion] [rama]`

este subira todos los commit al archivo origin

### Volver a un commit
`git reset --hard [codigo comit]`

## Estado y informacion de ramas

Informacion de la rama

- **Historia del repositorio:** `git log --all --decorate --oneline --graph`
- **Estado del local:** `git status`

## Clonar repositorio

Para clonar nesesitas la url del repositorio y copiara todo los datos del repositorio eso incluye archivos antiguos o antes subidos, para tener todos los commit hechos. Este archivo se clona en la carpeta o direccion en la que estes alojado.

`git clone [url]`

## Manipular ramas

Primero lo primero para saber que ramas tienes puede el siguiente comando

`git branch` o  `git branch --list`

de esta forma tendras un listado de toda tus ramas

### Crear rama

para que crear ramas, lo util de esas ramas es que te permiten modificarlas sin tener que modificar la rama principal haciendo que no arruines o alguien arruine la rama principal, de esta forma tu proyecto puede ser modificado de forma segura.

`git branch [nombre]`

### Cambiar nombre

Aveces uno quiere cambiar el nombre de su rama, bueno la forma de hacerlo es la siguiente. 

`git branch -m [Nuevo nombre]`

**Pero recuerda que esta forma es para la rama en la que estas ubicado**

### Eliminar rama
Hay dos formas de borrar una rama la forzada y la normal, la diferencia radica en que una te deja borrar apesar de que no allas hecho una fusion, mientras que la otra no te deja si no fusionaste la rama.

Normal|forzado
--|--
`git branch -d [rama]`|`git branch -D [rama]`

### Enumerar ramas
`git branch -a` este comando enumera todas las ramas remotas.