# Instalar Qtile

Aqui veremos como instalar Qtile un entorno tiling/mosaico que recomiendo mucho.

Guia inspirada por [sismo](https://www.sismonda.com.ar/730-2020-06-02-qtile-ubuntu-20-04-tiling-windows-manager-y-xrdp/)

## Instalar paquetes necesarios

Primero tenemos que instalar paquetes que necesita qtile para funcionar.

Usaremos de ejemplo pacman pero el instalador depende de su distribucion

```
pacman -S xorg python3-xcffib python3-pip python3-cairocffi libcairo2 lightdm python3-psutil
```

despues de instalar exitosamente todos estos paquetes podremos instalar Qtile

`sudo pip3 install qtile`

### Configuraciones de qtile
ahora copiaremos las configuraciones por defaut de qtile. las cuales son el escritorio por defaut y algunos iconos para las configuraciones
```
mkdir -p ~/.config/qtile/

cp /usr/local/lib/python3.8/dist-packages/libqtile/resources/default_config.py ~/.config/qtile/config.py

cp -r /usr/local/lib/python3.8/dist-packages/libqtile/resources/layout-icons/ .config/qtile/icons

```
### ejecutar qtile
ahora arremos que qtile sea ejecutado

```

sudo bash -c 'cat > /usr/share/xsessions/qtile-venv.desktop <<EOF
[Desktop Entry]
Name=Qtile(venv)
Comment=Qtile Session Within Venv
Exec=/usr/local/bin/qtile start
Type=Application
Keywords=wm;tiling
EOF'

```

lo que hace esto es generar el archivo qtile-venv.desktop con los datos que necesita para ejecutarce

desde el [desktop Entry] para abajo puedes copiarlo y te ara el mismo efecto siempre que lo crees en el lugar correcto.
### instalar herramientas
ya de aqui podemos instalar nuestras herramientas de preferencia

en mi caso sera Rofi, ranger, vim, neovim, kitty y opera.

`sudo pacman -S rofi ranger vim neovim kitty opera`

toda herramieta es bajo su propia preferencia 


## Errores de aranque

en caso de que tengas algun error de aranque pued ser por falta de librerias en confing.py que estara en ~/.config/qtile/config.py

```
import os
import re
import socket
import subprocess
from libqtile import qtile
from libqtile.config import Click, Drag, Group, KeyChord, Key, Match, Screen
from libqtile.command import lazy
from libqtile import layout, bar, widget, hook
from libqtile.lazy import lazy
from libqtile.utils import guess_terminal
from typing import List
```

esas son las librerias que tiene que tener para ejecutar correctamente

## Configuraciones

aqui te tengo una configuraciones de [antonio sarosi](https://github.com/antoniosarosi/dotfiles/blob/master/.config/qtile/README.es.md)

las cuales son las que usare pero puedes usar las que mas te gusten o inspirarte en ellas para tu configuracion final
