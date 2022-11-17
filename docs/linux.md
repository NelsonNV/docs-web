# linux

## Distros Recomendadas

- [Debian](https://www.debian.org): mejor distro para personalizar y usar en el trabajo
- [Ubuntu](https://ubuntu.com/download): si es la primera vez que usa linux bueno para uso de usuario y trabajo.
- [linux lite](https://www.linuxliteos.com): en caso de que quieras un linux que consuma poco pero basado en DEBIAN.
- [Kali](https://www.kali.org): para haking y petesting para uso de usuario no es recomendado
- [parrot](https://www.parrotsec.org): para haking o uso de usuario, tiene una version para uso de escritorio o trabajo.
- [Axyl os](https://axyl-os.github.io): Mejor distro de tiling que he visto para trabajo y otros (contruido en arch linux).

## Comandos basicos
Aqui miraras comandos mas simples pero utiles.
### Comandos para Moverte en terminal
Estos comandos son los mas utilizados al momento de moverte en la terminal.

Comando| Nota
---|---
`pwd`|Retorna la direcion donde estas en la terminal
`cd [direccion]`| Para moverte de carpeta
`ls` | Archivos dentro de la carpeta
`ll` | Igual que el **ls** pero te retorna como lista, que es igual a `ls -l` 


### copiar archivo o carpeta
Sintaxis: `cp [archivo a copiar] [ruta a pegar] `

Ejemplo: `cp ~/texto.txt ~/Documents/` 

Con esto se copia el **texto.txt** ala carpeta **Documents**
### Mover archivo o carpeta
Sintaxis: `mv [direcion archivo] [ruta nueva]`
### Eliminar
**Cuidado con el siguiente comando borrar en terminal es permanente**, no existe papelera en terminal, mucho cuidado.

La logica es la misma que muchos otros comandos empiesas con llamarlo y darle el nombre o hubicacion del archivo.

Sintaxis: `rm [archivo]` esta sintaxi borra archivos simples pero no carpetas para borrar una carpeta nesesitas agregar el parametro **-R** para borrar directorios o carpetas, pero te preguntara por cada archivo.
Si quieres borrar sin que te pregunte usa **-Rf** que fuerza o ignora la pregunta de ¿estas seguro?, Quedaria asi `rm -Rf [archivo]`

## Archivos comprimidos
Para descomprimir archivos necesitas algunas herramientas como unzip o unrar como tambien el comando `tar`, estos tendras que intalarlos si esque no estan. la instalacion depende de tu distro. Una recomendacion de archivos comprimidos es que manipules lo mas posible archivos **zip** ya que son los mas faciles de manipular y estan disponible tanto en windows como en linux, asi no te tienes que preocupar que no se pueda descomrpimir en otro equipo.

### Comprimir
Para comprimir archivos en linux es necesario que tengas instalado al menos un comprimidor de archivo. aqui te mostrare algunos comandos segun el tipo de archivo, hacerlo normal y con clave.

Archivo|Normal|Con Clave
--|--|--
zip|`zip [nombre].zip [archivo]`| 
rar|`rar -a [nombre].rar [archivo]`|
tar.gz|`tar -zcvf [nombre].tar.gz [archivo]`
.gz| `gzip -[1-9] [archivo no directorio]`


El parametro de gzip [1-9] es el nivel de seguridad que quieres

### Descomprimir
Descomprimir archivos es sencillo solo tienes que saber en donde esta tu archivo y si tiene clave.

Archivo|Paquete |Normal| Con Clave
--|--|--|--
.zip| unzip| `unzip [archivo]`| `unzip -p [password] [archivo]`
.rar| unrar| `unrar x [archivo] [extraer]` | `unzip -p [password] [archivo] [extraer en]`
.tar.bz| tar| `tar -xvf [archivo]`| No encontrado aun

## Crear archivos y carpetas
si quieres crear un archivo o carpeta tienes que usar unos comandos especificos
### crear archivo
para crear un archivo tienes que ejecutar el comando `touch` el cual esta es la sintaxis

`touch [archivo.extencion]`

como puedes ver es un comando muy simple y sencillo  en el que colocas su nombre y la extencion, tambien puedes decir en que hubicacion quieres crear el archivo pero eso seria algo como esto `touch ~/documento/archivo.txt` de esta forma sin importar donde este crearia en esa ubicacion.

### crear carpeta o directorio
Para crear carpeta es simple tienes que usar el comando `mkdir` es muy parecido al comando anterior, en el que colocas despues solo el nombre de la carpeta, y como en el anterior tambien puedes usar el donde quieres que se cree la carpeta

sintaxis: `mkdir [nombre]`

ejemplo: `mkdir ~/documento/codigo` con este le digo que en la carpeta documento cree una carpeta con el nombre codigo

## Guardar datos de un comando en archivo

este es facil de usar y nada complejo de entender, para que sirve en primer lugar, hay casos en lo que quieres crear por ejemplo un archivo con unos datos ya inglesados o quieres guardar los datos que te retorna algun comando, para eso usaresmos los siguientes simbolos `>` y `>>`
que serian lo siguiente.

`>` | `>>`
--|--
guarda o remplaza los datos en un archivo| agrega los datos en un archivo

un ejemplo seria querer guardar los datos de tu pc de ``neofetch`` para eso tendrias que usar la siguiente formula `neofetch > datopc.txt` con esto digo que quiero guardar los que me tire neofetch en un archivo llamado datopc.txt y de esta forma puedes guardar los datos de forma rapida.

sintaxi: `[comando o dato] [>/>>] [nombre y extencion]`



## Crear Ejecutable de appimagen o programas

para crear esto necesitaras ir ala carpeta `$HOME/.local/share/applications/` 
en esa carpeta tienes que crear un archivo.desktop

esta seria la sintaxis de su creacion


```desktop
[Desktop Entry]
Type=Application
Name=RPCS3
Comment=RPCS3
Icon=/home/usuario/.images/rpcs3.png
Exec=/home/usuario/AppImages/rpcs3.AppImage
Terminal=false
Catagories=Games
```

ahora si aparecera en arancadores de programas como rofi y dmenu.

[Fuente de la informacion](https://www.reddit.com/r/linuxquestions/comments/f1909s/run_appimage_from_launcher/)












