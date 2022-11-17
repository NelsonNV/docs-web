MKDOCS
=====================   

**Documentacion oficial [mkdocs.org](https://www.mkdocs.org)**


Esta es una herramienta que nos permite generar documentacion apartir de archivo **.md** o **Markdown**
esto nos permite crear de forma facil y sensilla documentos de nuestros proyectos

## Heramientas a utilizar

Nesesitaras tener [python](https://www.python.org/downloads/) instalado ya que es lo que usaremos para generar la documentacion.

Como la terminal de preferencia.
### Instalar mkdocs

Para instalar makdocs tienes que usar el siguiente comando:

``pip install mkdocs``

Para comprobar que se instaldo de forma exitosa ejecuta `mkdocs --version` te mostrara algo como esto

```bash
$ mkdocs --version
--resultado--
mkdocs, version 1.3.0 <dato extras>
```
## Crear Documento
Para generar un documento mkdocs tendras que ejecutar:

`$ mkdocs new [nombre proyecto]` o `mkdocs new .`
El ``.`` hace referencia a la direcion actual de tu terminal.

Ya creado el proyecto puedes tendras algo como esto:
```bash
mkdoc-generado
├────docs
│    └──index.md
└─mkdocs.yml
```

en la carpeta **docs** debes generar todos los documentos que quieras modificar y crear.

### Ejecutar proyecto
Para ver el proyecto de forma local ejecuta `mkdocs serve`
te  dira que en la direcion 127.0.0.1/8000 estara montado tu documento.

Cada cambio que hagas la pagina se actualizara automaticamente.

## Cambiar tema

Como lo habras notado el documento tiene un thema nada parecido al read the docs, esto es opcional pero si quieres cambiarlo modifica el archivo mkdocs.yml
 y agregale en alguna linea lo siguiente

```theme: readthedocs```

## Agregar indices

Igual o parecido al [cambiar tema](#cambiar-tema) tienes que agregar lo siguiente al archivo **mkdocs.md**

```yml
nav:
  - Inicio: 'index.md'
  - <nuevo indice>: '<documento>.md'
```

Como se puede ver al crear un indice tienes que vincularlo a un documento de la carpeta docs
el mkdocs agarra por defaut los archivo de esa carpeta por lo que solo tienes que mensionarlos
### Sub indices
los sub indices son los titulos secundarios del documento **Markdown** por lo que al usar # que es igual al `<h1>` del HTML5 el primero es el titulo cada  colocas ## seria `<h2>` y lo mismo con `<h3>`.

## Subir a Servidor

Una forma facil que encontre para subirla al servidor o para tener un modelo html es usar el comando `build`. El cual crea una carpeta llamada **site** en la que te guardara html, js, css y img de forma ordenada y listo para subir.

`mkdocs build`

Al ya tener tu documento solo tendrias que subirlo en tu hosting ya si quieres usando [filezilla](https://filezilla-project.org) o cualquier metodo que mas te acomode.
