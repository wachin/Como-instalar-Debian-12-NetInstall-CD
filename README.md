# Cómo instalar Debian NetInstall CD

Diríjase a la siguiente dirección donde en el 2024 está Debian 12 bookworm y allí busque Netinstall CD

https://www.debian.org/CD/netinst/

Como este tutorial está hecho con la versión Debian 12 bookworm alternativamente puede entrar en (y buscar Netinstall CD: 

https://www.debian.org/releases/bookworm/debian-installer/

## Ventoy para Bootear Debian
Después de descargada la ISO la puse en un pendrive en Ventoy, vea el siguiente tutorial: 

**Creando pendrive USB Multiboot con Ventoy desde Linux**  
https://facilitarelsoftwarelibre.blogspot.com/2021/12/creando-pendrive-usb-multiboot-con-ventoy-desde-linux.html

luego encendí el ordenador y lo arranqué desde el USB (que yo ya lo tenía preconfigurado para eso), y lo conecté al cable de red para que en el proceso de instalación se descarguen más rápido los paquetes

# Al iniciar el instalador elegir Graphical Install

Al aparecer el Grub de Ventoy elegir la 1er opción:

**Graphical Install**

>**Nota**: No demorarse mucho porque sino se ejecuta el modo de instalación desde la terminal.

Ahora, clic en:

**Select language:**

**Spanish - Español**

En país pongo mi país Ecuador

En teclado, explico, yo no tengo un teclado "Latinoamericano". Donde vivo en Ecuador núnca he visto que vendan en ninguna tienda, sino solo teclados en Español, asi que así elijo uno para que coincidan los dibujos de los elementos del teclado con el carácter que se obtendrá al presionar una tecla 

Durante la instalación me pregunta si me conecto desde el Wi-Fi o desde el cable de Red

>**Nota**: Tomele una foto con el celular ya que muestra el nombre de los dispositivos y puede que sirva después.

y le pongo que me conectaré desde el cable de red pues es más rapido.

Luego en:

**Configurar la red**

Me pregunta qué pongo en el nombre de la máquina, cambio el que tiene (dice debian) por: netinst (bueno, puede ser otro nombre).

El nombre de dominio me lo invento así como dice allí (le pongo hogar)

Después en:

**Configurar usuarios y contraseñas**

pongo una contraseña para el superusuario (root)

Luego me pide mi nombre completo, lo pongo

Luego:

**Nombre de usuario y contraseña**

o sea la contraseña del usuario normal, no la de root. Cada usuario debe tener su propia contraseña

Luego la 

**Zona horaria**

Y en:

**Particionado e discos**

Le pongo:

**Guiado - utilizar todo el disco**

Y Elijo el disco a particionar

Usted puede elegir el Disco de su ordenador, yo elegiré mi Pendrive pues lo voy a instalar allí para usarlo en varios ordenadores

Siguiente, elijo: 

**Todos los ficheros en una partición (recomendado para novatos)**

y siguiente, y aparecen muchas opiniones de las particiones, y abajo abajo al final dice: 

**"Finalizar el particionado y escribir los cambios al disco"**

Continuar

Me pregunta: 

**"Se escribirán en los discos todos los cambios . . . "**

**"Desea escribir . . . "**

debo ver bien en cuál unidad lo estoy instalando, pues como lo estoy instalando en un pendrive veo que es: 

/dev/sdc

>**Nota**: Ese sdc puede variar.

eso lo necesito saber para el final cuando pide instalar el grub, así que lo anoto en un papel

Marco que "si"

Y continuo

Y dice: 

**Instanlado el sistema base**

A las **10H05** empieza la instalación

Durante la instalación siempre hay que estar pendiente pues pregunta varias cosas y si uno no está para darle siguiente pues nunca se instala

**10H23**

**Configurar Gestor de Paquetes**

No hay de mi país, pero pongo uno cerca 

Me pregunta por: 

**Replica de debian**

Lo dejo en la primer opción

Me pregunta por la proxy, dejo vacío y Continuo

Y a esperar

**10H42**

Me pregunta: 

**popularity contest**

Le pongo que si

**Selección de programas**

## Eligiendo un Gestor / Entorno de Escritorio

Desmarco las siguientes:

**Entorno de escritorio Debian**-
**. . . GNOME**
**..y desmarco el resto**

Pero ustedes pueden marcar algun otro Gestor de Escritorio  y se así ahorran tiempo de configuración

y dejo marcado:

**Utilidades estándares del sistema**

**10h49**

**Instalando el cargador de arranque GRUB**

Me pregunta:

"Se han detectado en el sistema los sistemas operativos mostrados a continuación: Windows Vista, MX 21.3
Wildflower (21.3)
Si arriba se indican todos sus sistemas operativos, puede instalar con seguridad el cargador de arranque en su unidad principal (en la partición UEFI o el registro de arranque). Cuando el ordenador arranque de nuevo podrá escoger iniciar cualquiera de esos sistemas operativos o su nuevo sistema.
¿Desea instalar el cargador de arranque GRUB en su unidad principal?
No
Si"

Le pongo que: **Si**

>**Nota**: Si por le pongo que no, no funcionará después pues no aparecerá  el Grub al reiniciar, pero eso se soluciona con el Live USB de MX Linux (sea de 32 o 64  bit según el que este usando) con la opción de "Reparar inicio" de las herramientas de MX Linux.

Luego me pregunta: 

"Instalando el cargador de arranque GRUB Ahora debe configurar el sistema recién instalado para que sea arrancable, instalando para ello el cargador GRUB en un dispositivo del que se pueda arrancar. La forma habitual de hacerlo es instalar GRUB en su unidad principal (partición UEFI o registro principal de arranque). Si lo prefiere, puede instalar GRUB en cualquier otra unidad (o partición), o incluso en un medio removible.
Dispositivo donde instalar el cargador de arranque:
Introducir el dispositivo manualmente
/dev/sda (ata-SAMSUNG_SP2504C_S09QJ1DP502191)
/dev/sdb (usb-SanDisk Cruzer_Blade_04017921042721204743-0:0)
/dev/sdc (usb-SanDisk_Cruzer_Force_4C530000230514216185-0:0)"

Y aquí es donde necesito lo que anoté arriba: 

/dev/sdc

Lo selecciono ese y lo instalo

**Terminar la instalación**

Retiro el pendrive donde está Ventoy

Y **Continuar**

Se reinicia, booteo desde el pendrive del ordenador

Ahorita reinicio y si puedo entrar, como no instalé ninguna interfaz gráfica ni la de debian mismo entonces solo aparece una terminal (no hay ninguna interfaz gráfica). La terminal que aparece dice: 

```
Debian/Linux 12 netinst tty1`

netinst login: _
```

allí poner el nombre de usuario, y luego dice: 

password:

Ponga la contraseña de ese usuario y de Enter y aparece en mi caso: 

```
wachin@netinst:^$
```

ahora debemos escribir:

```
su
```

y poner la contraseña de superusuario (root) 

ahora me aparece así: 

```
root@netinst:/home/wachin#
```

y allí poner:

```
apt update
```

**11H10**

luego instalar los programas necesarios, como yo no instale ningún Gestor de Ventanas debo instalar manualmente todos las parques para que un Sistema Operativo Linux funcione adecuadamente, enfocándome en KDE (pues eso es lo que quiero):

```
apt install sudo adduser ucf kate kdenlive \
    libreoffice default-jre accountsservice \
    locate xdg-user-dirs xdg-user-dirs-gtk \
    pkexec dbus-user-session udev kde-cli-tools \
    dolphin kde-baseapps kate konsole synaptic \
    polkit-kde-agent-1 pavucontrol paprefs \
    xserver-xorg-input-multitouch exo-utils \
    baobab network-manager network-manager-gnome \
    firmware-linux-free firmware-misc-nonfree \
    tree acpi quick-system-info-gui \
    hardinfo memtest86+
```

## Paquete Test de memoria
Este paquete memtest86+ es para que en el Grub se genere el menú de el "Test de memoria" debe estar instalado el paquete:

memtest86+

# Generar los locales e instalar el Administrador de inicio de sesión
Si usted desea usar más de un idioma en su sistema operativo y que este esté disponible en el administrador de inicio de sesión (Login Manager) debe configurarlo poniendo en la terminal (como usario root): 

```
dpkg-reconfigure locales
```

seleccione de la lista los que desea usar, en mi caso yo solo necesito además del español el inglés y lo selecciono y con TAB me ubico en Aceptar y doy Enter. A continuación elijo el idioma por defecto, en mi caso:

```
es_EC.UTF-8
```

luego instalo el Login Manager, yo usaré lxdm:

```
apt install lxdm
```

>**Nota**: También se puede usar lightdm (MX Linux lo usa con lightdm-gtk-greeter)

al seguir este orden así, al reiniciar estarán disponibles los idiomas que hayamos generado (de lo contrario no)

# CONTROLADORES DEL TOUCHPAD DE LAPTOP DELL
El controlador del touchpad para Dell Inspiron 1750. En mi laptop Dell Inspiron 1750 no funciona el doble clic del touchpad en Debian 12 con el paquete:

```
xserver-xorg-input-synaptics
```

pero puedo instalarlo de todos modos, y ya lo arreglo después pues he hecho una solución en:

**No funciona doble clic en Touchpad Dell Inspiron 1750 en Debian 12**  
https://facilitarelsoftwarelibre.blogspot.com/2024/08/no-funciona-doble-clic-en-touchpad-dell-inspiron-1750-en-debian-12.html


# INSTALO PAQUETES alsa (ESTA PALABRA BUSCADA EN SYNAPTIC) PRESENTES EN MX LINUX 21 DE 32 BIT
Estos me hacian falta para que el volumen en el mixer pnmixer apareciera activado al encender el ordenador, esto pues cuando yo lo encendía e iniciaba sesión el volumen del icono de pnmixer estaba silenciado y revisando el volumen estaba marcado como apagado, tenía que subirlo manualmente para escuchar algo, pero 
instalando lo siguiente ya funiona:

```
apt install alsa-tools alsa-utils gstreamer1.0-alsa \
    libatopology2 volumeicon-alsa
```

También sospecho que estos paquetes me hacía falta instalar para que funcione QjackCtl con Pulseaudio (porque no me funcionaba)

# INSTALO PAQUETES dbus (ESTA PALABRA BUSCADA EN SYNAPTIC) PRESENTES EN MX LINUX 21 DE 32 BIT
De la lista me faltaban por instalar:

```
dbus-x11 xdg-dbus-proxy
```

son importantes para el sistema, para la comunicación de aplicaciones entre si y el sistema operativo.


# LAS SIGUIENTES ES POSIBLE QUE YA SE HAYAN INSTALADO

```
sudo apt install base-passwd passwd dmsetup
```

sirven para la gestión de usuarios y sus contraseñas


# DEPENDENCIAS PARA FLUXBOX
Instalo lo siguiente:

```
apt-get install git fluxbox lxappearance lxrandr \
    pnmixer numlockx xfce4-appfinder qt5ct \
    nitrogen gnome-icon-theme frameworkintegration gxkb
```

## Configurar Fluxbox 
Yo voy a clonar mi Repositorio de Fluxbox e indicarle que se renombre a .fluxbox escribiendo a mano así en la terminal:


```
git clone https://github.com/wachin/RisenPC-Flux-Deb12-NetInstCD-KDE .Fluxbox
```

Y doy Enter, y reinicio en ordenador con el botón de reinicio o sino apagandolo y volviéndolo a encender, y ahora sí entro en la sesión de Fluxbox

Si uno desea lanzar Synaptic desde root, poner:
```
su
```
y la contraseña, y poner: 

```
synaptic-pkexec
```
PARA INSTALAR EL ADMINISTRADOR DE ARCHIVOS DOLPHIN

```
sudo apt install dolphin kde-baseapps konsole kde-cli-tools \
     kio-extras kdegraphics-thumbnailers ffmpegthumbs ark \
     kde-style-oxygen-qt5 kde-style-qtcurve-qt5 breeze \
     papirus-icon-theme oxygen-icon-theme qt5-style-kvantum \
     usb.ids mtp-tools qdbus-qt5 qt5ct
```

### APLICACIONES
Y además estas aplicaciones:

```
sudo apt install frameworkintegration chromium \
    partitionmanager kdf qapt-deb-installer \
    meld gwenview okular qps kompare pyzo \
    screengrab gpick qbittorrent novelwriter \
    keepassxc krusader catfish hardinfo2 \
    xvkbd xfce4-notes
```

### Username Is Not In The Sudoers File

Debemos arreglar el que no podemos usar sudo, para eso poner:

```
su -
```
Luego debe entender el siguiente ejemplo:

usermod -aG sudo suusuario

porque debe de cambiar allí donde dice "usuario" por el suyo

Si no sabe cuál es el nombre usuario, le explico que es el nombre que está a la izquierda de la @ en la terminal

En mi caso tu pongo

```
su -
```

y luego:

```
usermod -aG sudo wachin
```
porque mi usuario es "wachin" (en su usuario debe ser otro)

**reiniciar**

y reinicio

Ejecutar la herramientas del sistema: 

`xdg-user-dirs-update`

eso es para que aparezcan las carpetas: Descargas, Música, Video y otras


# OTRAS APLICACIONES

Faltan por instalar algunas cosas del sistema, en synaptic marcar para instalar:

cups
colord
kcalc
ktimer
lynx
print-manager
sane-utils
sweeper
kcharselect
ipp-usb


# DEPENDENCIAS PARA OTROS KERNEL 
Para instalar otros kernel:
```
sudo apt install gcc dkms
```
Ejemplo yo he compilado unos Kernel personalizados y es necesario estos paquetes para poderlos instalar.


# CÓMO INSTALAR EL CONTROLADOR DE WI-FI EN ORDENADORES EN QUE FALTA EL DRIVER POR SER PRIVATIVO
Para instalar el controlador del Wi-Fi para esta laptop Dell Inspiron 1750 que tiene un controlador privativo sigo las siguientes instrucciones:

**Cómo instalar el controlador del Wi-Fi en Debian 11, 12 KDE (ejemplo para mi Laptop Dell Inspiron 1750)**  
https://facilitarelsoftwarelibre.blogspot.com/2023/11/como-instalar-controlador-privativo-del-wi-fi-en-debian.html

para mí laptop instalo broadcom:

firmware-b43-installer

Cierro sesión y vuelvo a entrar y ya funciona


# CÓMO ARREGLAR EL TOUCHPAD DE MI LAPTOP DELL INSPIRON EN DEBIAN 12
Sigo estas  instrucciones:

**No funciona el Touchpad de mi laptop Dell Inspiron 1750 en Q4OS 4 Gemini**  
https://facilitarelsoftwarelibre.blogspot.com/2023/11/blog-post_12.html


# PROGRAMAS DE PYTHON
Para que funcionen algunos programas de python pueden instalarse los siguientes paquetes:

```
sudo apt install python3-brotli python3-bs4 \
    python3-cairo python3-certifi python3-chardet \
    python3-cups python3-cupshelpers python3-dbus \
    python3-distro python3-gi python3-html5lib \
    python3-lxml python3-mutagen python3-packaging \
    python3-ply python3-pycryptodome python3-pyqt5 \
    python3-pyqt5.sip python3-pyxattr python3-sip \
    python3-sipbuild python3-six python3-smbc \
    python3-soupsieve python3-toml \
    python3-webencodings python3-websockets \
    python3-xdg
```

# PROGRAMAS NO USADOS EN ESTÁ INSTALACIÓN
No creo tener la necesidad de instalar lo siguiente:

xdg-document-portal
xdg-desktop-portal-gtk
xdg-dbus-proxy

pero no descarto instalarlos después si los necesite.

Los siguientes paquetes no son necesarios:

gvfs  
gvfs-common  
gvfs-daemons  
gvfs-libs

porque solo voy a usar Dolphin como administrador de archivos:

**Instalar correctamente Dolphin (Administrador de archivos) en MX Linux, antiX basados en Debian en entornos no KDE (tal vez basados en Ubuntu también)**  
https://facilitarelsoftwarelibre.blogspot.com/2019/11/instalar-correctamente-dolphin-en-entornos-no-kde.html

Dios los bendiga
