# Cómo instalar Debian NetInstall CD

Diríjase a la siguiente dirección donde en el 2024 está Debian 12 bookworm y allí busque Netinstall CD

[https://www.debian.org/CD/netinst/](https://www.debian.org/CD/netinst/)

Como este tutorial está hecho con la versión Debian 12 bookworm alternativamente puede entrar en (y buscar Netinstall CD: 

[https://www.debian.org/releases/bookworm/debian-installer/](https://www.debian.org/releases/bookworm/debian-installer/)

## Ventoy para Bootear Debian
Después de descargada la ISO la puse en un pendrive en Ventoy, vea el siguiente tutorial: 

**Creando pendrive USB Multiboot con Ventoy desde Linux**  
[https://facilitarelsoftwarelibre.blogspot.com/2021/12/creando-pendrive-usb-multiboot-con-ventoy-desde-linux.html](https://facilitarelsoftwarelibre.blogspot.com/2021/12/creando-pendrive-usb-multiboot-con-ventoy-desde-linux.html)

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

o sea la contraseña del usuario normal (no la de root). Cada usuario debe tener su propia contraseña

Luego la 

**Zona horaria**

Y en:

**Particionado e discos**

Aquí hay una situación, se puede usar todo el disco pero se borrará todo lo que esté en el Disco de Almacenamiento (HDD, SSD, NVM, u otro). En mi caso voy a usar todo el disco (luego haré otra explicación para instalar junto a Windows), le pongo:

**Guiado - utilizar todo el disco**

Y Elijo el disco a particionar

# Instalar en el Disco del ordenador
Elija el Disco de su ordenador para que lo instale allí

Siguiente, elijo: 

**Todos los ficheros en una partición (recomendado para novatos)**

y siguiente, y aparecen muchas opiniones de las particiones, y abajo abajo al final dice: 

**"Finalizar el particionado y escribir los cambios al disco"**

Continuar

Me pregunta: 

**"Se escribirán en los discos todos los cambios . . . "**

**"Desea escribir . . . "**

debo ver bien en cuál unidad lo estoy instalando, debe ser en: 

/dev/sda

eso lo necesito saber para el final cuando pide instalar el grub, así que lo anoto en un papel

Marco que "si"

Y continuo

Y dice: 

**Instanlado el sistema base y otros**

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

Le pongo que si (usted si desea puede poner que no)

**Selección de programas**

## Eligiendo un Gestor / Entorno de Escritorio

Si dejan como está:

**Entorno de escritorio Debian**-
**. . . GNOME**

se instalará GNOME, pero si los desmarcan esos dos y marcan alguno de los otros se instalará aquel que elijan

yo he estado probando:

- XFCE  
- LXDE  
- LXQT  
- KDE  

estos tres me parecen muy interesantes, de estos KDE usa más recursos pero si los tuviera el ordenador preferible para mi este, y sino pues LXQT o XFCE

Pero ustedes pueden marcar algun Gestor de Escritorio que quieran

yo dejo marcado:

"Utilidades estándares del sistema"

y elijo

XFCE

10h45

10h49

**"Instalando el cargador de arranque GRUB"**

Me pregunta:

"Se han detectado en el sistema los sistemas operativos mostrados a continuación: Windows Vista, MX 21.3
Wildflower (21.3)
Si arriba se indican todos sus sistemas operativos, puede instalar con seguridad el cargador de arranque en su unidad principal (en la partición UEFI o el registro de arranque). Cuando el ordenador arranque de nuevo podrá escoger iniciar cualquiera de esos sistemas operativos o su nuevo sistema.
¿Desea instalar el cargador de arranque GRUB en su unidad principal?
No
Si"

Le pongo que: Si

**Nota:** Si por le pongo que no, no funcionará después pues no aparecerá  el Grub al reiniciar, pero eso se soluciona con el Live USB de MX Linux (sea de 32 o 64  bit según el que este usando) con la opción de "Reparar inicio" de las herramientas de MX Linux.

Luego me pregunta: 

"Instalando el cargador de arranque GRUB Ahora debe configurar el sistema recién instalado para que sea arrancable, instalando para ello el cargador GRUB en un dispositivo del que se pueda arrancar. La forma habitual de hacerlo es instalar GRUB en su unidad principal (partición UEFI o registro principal de arranque). Si lo prefiere, puede instalar GRUB en cualquier otra unidad (o partición), o incluso en un medio removible.
Dispositivo donde instalar el cargador de arranque:
Introducir el dispositivo manualmente
/dev/sda (ata-SAMSUNG_SP2504C_S09QJ1DP502191)
/dev/sdb (usb-SanDisk Cruzer_Blade_04017921042721204743-0:0)

Y aquí es donde necesito lo que anoté arriba: 

/dev/sda

En ese lo instalo, siempre **sda** es el disco de almacenamiento del ordenador o laptop

"Terminar la instalación"

**Reinicio**, Retiro el pendrive donde está Ventoy

Y entro y continuar

**10h49**

### Username Is Not In The Sudoers File

Al entrar debemos arreglar el que no podemos usar sudo, para eso poner:

```bash
su -
```
Luego debe entender el siguiente ejemplo:

```bash
usermod -aG sudo suusuario
```

porque debe de cambiar allí donde dice "suusuario" por el suyo

Si no sabe cuál es el nombre usuario, le explico que es el nombre que está a la izquierda de la @ en la terminal

En mi caso yu pongo

```bash
su -
```

y luego:

```bash
usermod -aG sudo wachin
```
porque mi usuario es "wachin" (en su usuario debe ser otro)

**reiniciar**

y reinicio, pues así ya puedo usar el Linux como siempre lo he usado en Ubuntu, MX Linux. Y explico que, en debian aparece el mensaje "El nombre de usuario no está en el archivo sudoers" por cosas de los usuarios avanzados de Debian, ellos entrar en root con "su -" y poner la contraseña de superusuario root y desde allí trabajar directamente.

También es posible necesitar:

### Instalé Debian 12 Netinstall con LXQT pero en la Laptop Dell Inspiron 14 3481 no puedo regular el Brillo con teclas F11 o F12  
[https://facilitarelsoftwarelibre.blogspot.com/2025/07/teclas-f-de-brillo-en-laptop-no-funcionan-en-debian-12-netinstall-cd.html](https://facilitarelsoftwarelibre.blogspot.com/2025/07/teclas-f-de-brillo-en-laptop-no-funcionan-en-debian-12-netinstall-cd.html)

### CÓMO INSTALAR EL CONTROLADOR DE WI-FI EN ORDENADORES EN QUE FALTA EL DRIVER POR SER PRIVATIVO
Tengo una laptop Dell Inspiron 1750 que tiene un controlador privativo, aquí dejo un tutorial de cómo lo pude solucionar:

**Cómo instalar el controlador del Wi-Fi en Debian 11, 12 KDE (ejemplo para mi Laptop Dell Inspiron 1750)**  
[https://facilitarelsoftwarelibre.blogspot.com/2023/11/como-instalar-controlador-privativo-del-wi-fi-en-debian.html](https://facilitarelsoftwarelibre.blogspot.com/2023/11/como-instalar-controlador-privativo-del-wi-fi-en-debian.html)

para mí laptop que tiene el driver broadcom:

firmware-b43-installer

Cierro sesión y vuelvo a entrar y ya funciona


# CÓMO ARREGLAR EL TOUCHPAD DE MI LAPTOP DELL INSPIRON EN DEBIAN 12
En Debian 12 el touchpad de mi laptop Dell Inspiron 1750 tiene un problema, para arreglarlo sigo estas instrucciones:

**Doble clic en Touchpad Dell inspiron 1750 no funciona en Debian 12**
[https://facilitarelsoftwarelibre.blogspot.com/2024/08/no-funciona-doble-clic-en-touchpad-dell-inspiron-1750-en-debian-12.html](https://facilitarelsoftwarelibre.blogspot.com/2024/08/no-funciona-doble-clic-en-touchpad-dell-inspiron-1750-en-debian-12.html)


Dios los bendiga
