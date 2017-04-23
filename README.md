# calendar.venezuela

Recordatorio de fechas relevantes para los habitantes de la República Bolivariana de Venezuela.

Obra compatible con el formato de recordatorios del comando **calendar** incluido en el paquete
**bsdmainutils** que se distribuye con GNU/Linux Ubuntu (a su vez derivado de Debian distro).

## Breve descripción sobre cómo "calendar" lee los ficheros de recordatorios.

El comando "calendar" obtiene  todos sus  datos de la carpeta **/usr/share/calendar/** donde se
encuentra alojado el ficehro **calendar.all** el cual contiene un listado de los demás ficheros
con recordatorios con la nomenclatura **calendar.extension** donde _extension_ describe el con-
tenido temático.

En todo caso el fichero **calendar.all** es  clave y dependiendo  donde esté ubicado primero se
lee y ejecuta. A su vez dentro de cada fichero **calendar.extension** se puede hacer referencia
a otra subcarpeta que tiene **_otro_ fichero calendar.all** que describe otros subficheros.

Aunque no es oficial esta  estructura jerárquica que presentamos a continuación, es nuestra ma-
nera de representar rápida y fácilmente la manera de trabajar de **calendar**:

	------------------------
	~/.calendar/            | 1° en ser leído y ejecutado
	   /etc/calendar/       | 2° si no existe 1° entonces lee y ejecuta esta carpeta.
	    /usr/share/calendar/| 3° por último,de no conseguir ni 1° ni 2° lee y ejecuta esta carpeta
	------------------------+/calendar.all
	                                  |-calendar.world
	                                  |-calendar.argentina
	                                  |-calendar.australia
	                                  |-calendar.belgium
	                                  |-calendar.birthday
	                                  |-calendar.christian
	                                  |-calendar.computer
	                                  |-calendar.croatian
	                                  |         |-hr_HR/calendar.all
	                                  |                         |-hr_HR/calendar.praznici
	                                  |-calendar.debian
	                                  |-calendar.discordian
        	                          |-calendar.dutch
	                                  |-calendar.eu
	                                  |-calendar.freebsd
	                                  |-calendar.french
	                                  |         |-fr_FR/calendar.all
	                                  |                         |-fr_FR/calendar.jferies
	                                  |                         |-fr_FR/calendar.fetes
	                                  |                         |-fr_FR/calendar.proverbes
	                                  |-calendar.german
	                                  |         |-de_DE/calendar.all
	                                  |                         |-de_DE/calendar.kirche
	                                  |                         |-de_DE/calendar.wissenschaft
        	                          |                         |-de_DE/calendar.feiertag
	                                  |                         |-de_DE/calendar.literatur
	                                  |                         |-de_DE/calendar.geschichte
	                                  |                         |-de_DE/calendar.musik
	                                  |-calendar.history
	                                  |-calendar.holiday
	                                  |-calendar.hungarian
	                                  |         |-hu_HU/calendar.all
	                                  |                         |-hu_HU/calendar.nevnapok
	                                  |                         |-hu_HU/calendar.unnepek
	                                  |-calendar.judaic
	                                  |-calendar.kazakhstan
	                                  |-calendar.lotr
        	                          |-calendar.music
	                                  |-calendar.newzealand
	                                  |-calendar.pagan
	                                  |-calendar.russian
        	                          |         |-ru_RU/calendar.all
	                                  |                         |-ru_RU/calendar.holiday
	                                  |                         |-ru_RU/calendar.msk
	                                  |                         |-ru_RU/calendar.pagan
	                                  |                         |-ru_RU/calendar.common
	                                  |                         |-ru_RU/calendar.military
	                                  |                         |-ru_RU/calendar.orthodox
	                                  |-calendar.southafrica
	                                  |-calendar.thai
	                                  |-calendar.ubuntu
	                                  |-calendar.ukrainian
	                                  |         |-uk_UA/calendar.all
	                                  |                         |-uk_UA/calendar.holiday
	                                  |                         |-uk_UA/calendar.misc
	                                  |                         |-uk_UA/calendar.othodox
	                                  |-calendar.unitedkingdom
	                                  |-calendar.usholiday
	                                  |-_calendar.venezuela- (nuestra propuesta)_

## Instrucciones de instalación a nivel de usuario.

Para leer la historia completa sobre nuestra motivación para crear dicho fichero por favor vi-
sitad [este enlace web](http://www.ks7000.net.ve/2017/04/21/comandos-gnulinux-conocidos/).

Según instrucciones en fichero **calendar.all** debemos hacer lo siguiente:

* En nuestra carpeta personal debemos crear una carpeta oculta llamada "calendar".
* Para ello en una ventana terminal tecleamos **"mkdir ~/.calendar"**.
* Luego copiamos con el comando **sudo cp /usr/share/calendar.all ~/.calendar/calendar.all**.
* Editamos nuestro archivo personal **nano ~/.calendar/calendar.all** (o vuestro editor favorito).
* Agregamos la siguiente línea **#include <calendar.venezuela>**.
* (opcional):borramos las líneas que especifican ciertos ficheros **calendar.*** _que no nos interesan_.
* Guardamos y salimos del editor de texto.
* Descargamos de este repositorio el fichero **calendar.venezuela** a nuestra carpeta **~/calendar**.
* Para ver la ayuda del comando **calendar** tecleamos **man calendar** (y aprendemos como usarlo).
* Ejecutamos el comando **calendar** y verificamos si muestra los recordatorios.

Si seguimos estas instrucciones el comando **calendar** funcionará solo para el usuario actual.

## Instrucciones de instalación a nivel de partición.

Se deben seguir los mismos pasos que a nivel de usuario **pero en este caso usaremos -con derechos
de administrador "root"- a la carpeta /etc/calendar/**. La ventaja de este  método es que podremos
elevar de versión la distro que tengamos instalada o instalamos otra distro (suponiendo que tenga-
mos la carpeta /etc en una partición distinta o la tengamos respaldada en otro dispositivo)CONSER-
VANDO LA CONFIGURACIÓN QUE HAGAMOS.

La desventaja de este método es que se modifica para todos los usuarios en un mismo ordenador.

## Instrucciones de instalación a nivel de sistema operativo.

Con derechos de  administrador "root" modificamos  el fichero **/usr/share/calendar/calendar.all**
agregando la línea **#include <calendar.venezuela>** y copiando el fichero **calendar.venezuela** a
la carpeta **usr/share/calendar/**. La desventaja de este método es que se modifica para todos los
usuarios en un mismo ordenador.

## Para mayor información (en inglés):
* [bsdmainutils package at Debian](http://metadata.ftp-master.debian.org/changelogs/main/b/bsdmainutils/bsdmainutils_9.0.12+nmu1_copyright).
* [Package: bsdmainutils (9.0.6ubuntu3) ](http://packages.ubuntu.com/xenial/bsdmainutils).
* [File list of package bsdmainutils in xenial of architecture amd64](http://packages.ubuntu.com/xenial/amd64/bsdmainutils/filelist).
