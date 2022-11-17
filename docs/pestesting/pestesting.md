# Pestesting

material de como hacer pruebas de pestesting o estudios de bugneravilidades

## nmap

### que es 

nmap es una herramienta de escaneo de puertos, aunque paresca simple es la herramienta mas util al momento de iniciar un reconocimiento.

**pero esta herramienta no nos sirve si no conocemos algo de redes**

### algunos datos que podemos capturar con nmap

alguna de las informaciones que podemos tener son las siguientes:

- puerto
- servicio
- ttl
- version del servicio
- sistema operativo

estos datos lo podemos sacar con un escaneo muy espesifico

**Se necesita root**

`nmap -sV -O -vvv [ip]`

Se puede utilizar en algunos escaneo el dominio pero no siempre podremos sacar todos los datos como por ejemplo el escaneo de la SO.

hay funciones dentro del nmap como la busqueda de vugneravilidades y fuerza bruta.
todo esto en base a [script](https://nmap.org/book/nse-usage.html) ya existentes tenemps mucha informacion de esos script en la pagina oficial.

## Hackear una red wifi

usaremos la herramienta ``wifite``
### que es lo que hace wifite

wifite intenta sumprantar la red original para asi capturar la el hash de los paquetes enviados de esta forma solo quedaria desepcriptar la contraseña.

en palabras simple. campturamos la contraseña que esta encriptada. para despues desencriptarla.

Pero este metodo utiliza el hecho de que existe un dispositivo que intentara conectarse.
### como usarla

- esta herramienta necesita que instales algunos programas te lo menciona al inicio
- es necesario tener una tarjeta de red que pueda entrar en modo escaneo.

al ejecutar el ``wifite`` como root.

nos mostrara todas las redes que tenemos en nuestra red wifi. el cuanta redes y que nivel de señal tenga depende de tu antena.

precinaremos el ``ctrl + C`` para detener el proceso de escaneo, y le escribimos el numero en el que esta la red que queremos escanear

**re cordar que pregunta por el ultimo escaneo que se hizo**

al seleccionarla generara una prueba de captura de hash
con esto probara si la contraseña es posibre desifrarla, con su base de dato portable.

en caso de que funcione su desifrado generara un archivo json con la contraseña y una carpeta ``hs`` que contendra el hash de la red wifi

pero en caso de que no te funcione tendras que decifrar la contraseña con herramientas de cifrado
### fuente

todo esto fue basado en un [tutorial de internet](https://www.youtube.com/watch?v=cpz4yt4o7GM)

## Modo escaneo en la red wifi

usaremos la herramienta `airmon-ng` que nos permite controlar este estado en la red

suponiendo que la tarjeta de red es la wlan0 seria


- activar: ``airmon-ng start wlan0``
- decativar: ``airmon-ng stop wlan0`` en algunos casos sera wlan0mon su nombre de escaneo utilar `ifconfig` para ver su nombre.

### error de red

si no te activa o funciona la red otra vez puedes reiniciar el NetworkManager con el siguiente comando.

`systemctl resert NetworkManager`

de esta forma reiniciaremos el servicio de internet.


## desemcriptar

existe una herramienta llamada `aircrack-ng` que nos permitira probar el archivo.cap.

una forma de usarlo es la siguiente.

`aircrack-ng [archivo cap] -w wislist`

### wislist

si no sabes donde estan las wislist o no tiene una puedes encontrar en

``/usr/share/wislist``

o puedes crear la tulla con `crunch [rango min] [rango max] [cadena] -o [donde guardar]`