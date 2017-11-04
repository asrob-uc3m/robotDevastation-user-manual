# Instalar Robot Devastation - PC (Windows)

Para empezar, necesitarás un compilador de C++. Puedes descargar el último Visual Studio (Community edition) de la [página de Microsoft](https://www.visualstudio.com/downloads/). Para configurar y compilar proyectos de VS se usará CMake ([página de descargas](https://cmake.org/download/)).

## Descargar e instalar binarios de YARP

El software de RD está diseñado en torno a YARP. Si has instalado una versión de Visual Studio reciente, puedes descargar directamente los binarios precompilados de la [página de descargas de YARP](http://www.yarp.it/download.html) y pasar al apartado [#Descargar e instalar dependencias adicionales](#descargar-e-instalar-dependencias-adicionales). Alternativamente, puedes compilar ACE y YARP desde el código fuente.

## Descargar y compilar ACE desde el código fuente

El protocolo de comunicaciones de YARP está basado en [ACE](http://www.cs.wustl.edu/~schmidt/ACE.html). Descarga la última release *micro* de ACE desde [aquí](http://download.dre.vanderbilt.edu/), TAO no es necesario. Sigue las instrucciones en [Building and Installing ACE on Windows with Microsoft Visual Studio](http://www.dre.vanderbilt.edu/~schmidt/DOC_ROOT/ACE/ACE-INSTALL.html#msvc). Recuerda seleccionar la configuración *Release Win32* dentro de Visual Studio.

**Nota:** recomendamos lanzar la solución *ACE_wrappers* (en función del toolset de Visual Studio instalado, escogerás *ACE_wrappers_vc12.sln* o *ACE_wrappers_vc14.sln*) en lugar de *ACE* dado que la primera evitará que compiles un gran número de binarios que probablemente no vayas a necesitar, consiguiendo así reducir el tiempo total de compilación.

## Descargar y compilar YARP desde el código fuente

El código de YARP reside en [GitHub](https://github.com/robotology/yarp). Puedes descargarlo pulsando [aquí](https://github.com/robotology/yarp/archive/master.zip), o clonar el repositorio localmente con ayuda de tu cliente Git preferido.

Ahora, configura el proyecto VS:

1. Ejecuta la aplicación GUI de CMake.
2. En *Where is the source code*, indica la ruta al directorio donde has descomprimido/clonado YARP.
3. En *Where to build the binaries*, indica la ruta a un subdirectorio `/build` dentro del directorio anterior.
4. Haz clic en `Configure` y selecciona el toolset de Visual Studio que instalaste al inicio de esta guía. En caso de estar disponible, no selecciones la opción de 64 bits.
5. Proporciona la ruta al directorio de compilación de ACE en las opciones siguientes: `ACE_INCLUDE_DIR` debería apuntar al directorio *ACE_wrappers* (si no ha sido renombrado), y `ACE_ACE_LIBRARY_RELEASE` a *ACE_wrappers/lib/ACE.lib*.
6. Haz clic en `Generate` y `Open project` (si tu versión de CMake GUI incluye este botón) o dirígete al directorio `build` y haz clic en la solución de Visual Studio (busca la extensión *.sln*). Si quieres instalar YARP en la ruta por defecto (*C:\Program Files (x86)*), necesitarás lanzar Visual Studio con permisos de administrador, luego haz *Archivo>Abrir*, navega al directorio `build` y abre el fichero *.sln*.

**Nota (corregido en la futura release v2.3.72 de YARP):** es posible que ya dispongas de una copia de ACE dado que se distribuye junto con los binarios de YARP. En ese caso, CMake buscará en las rutas estándar y, probablemente, escogerá esta versión antes que los binarios que compilaste en la sección anterior, forzándote a introducir manualmente las rutas correspondientes en los valores de las entradas *ACE_INCLUDE_DIR*, *ACE_ACE_LIBRARY_RELEASE* y *ACE_ACE_LIBRARY_DEBUG* en la GUI de CMake. Sin embargo, CMake almacena algunas variables persistentes como resultado de una serie de inspecciones internas de las características disponibles de ACE, las cuales pueden diferir entre ambas versiones. Hemos observado que la variable *ACE_HAS_STRING_HASH* suele frustrar el proceso de compilación posterior si no es actualizada para reflejar el resultado de dichas inspecciones referidas a tu versión compilada de ACE (en lugar de la que es instalada junto con YARP). Para conseguirlo, elimina todas las ocurrencias de *ACE_HAS_STRING_HASH* en el archivo *CMakeCache.txt* dentro de tu directorio *build* y reinicia la GUI de CMake (es necesario ya que almacena su propia cache volátil). Después, haz clic de nuevo en `Configure` y `Generate`.

En Visual Studio, selecciona la configuración *Release* y compila la solución. Para instalar YARP (no es obligatorio), compila el proyecto *INSTALL* desde el explorador de soluciones.

## Descargar e instalar dependencias adicionales

RD depende de las siguientes librerías:
* [SDL 2.0](https://www.libsdl.org/index.php) ([página de descargas](https://www.libsdl.org/download-2.0.php))
* [SDL_image 2.0](https://www.libsdl.org/projects/SDL_image/)
* [SDL_mixer 2.0](https://www.libsdl.org/projects/SDL_mixer/)
* [SDL_ttf 2.0](https://www.libsdl.org/projects/SDL_ttf/)
* [ZBar](http://zbar.sourceforge.net/) ([enlace de descarga](https://sourceforge.net/projects/zbar/files/latest/download), [mirror de asrob-uc3m](https://github.com/asrob-uc3m/ZBar/releases/latest))

Descomprime/instala estas librerías en las rutas de tu elección, las necesitarás más adelante.

## Compilar Robot Devastation

Lanza CMake GUI y sigue los puntos del 1 al 3 en [#Descargar y compilar YARP desde el código fuente](#descargar-y-compilar-yarp-desde-el-código-fuente) para preparar el build de RD en la ruta deseada. Después de pulsar en `Configure`, CMake te advertirá de algunas variables de configuración relativas a las dependencias listadas anteriormente que no ha sido capaz de detectar y que tendrás que especificar manualmente para poder continuar, volviendo a darle al botón `Configure`. Este proceso será repetido hasta que no aparezcan más errores. Abre la solución de Visual Studio, selecciona la configuración *Release* y compila.

## Configurar las rutas en tiempo de ejecución

La ubicación de las librerías dinámicas (archivos con la extensión *.dll*) listadas como dependencias deberían ser añadidas a la variable de entorno *PATH* para poder enlazarlas en tiempo de ejecución con los programas de YARP y RD (ficheros *.exe*). Esta configuración se puede ajustar en *Equipo>Propiedades>Configuración avanzada del sistema>Opciones avanzadas>Variables de entorno*. Alternativamente, puedes simplemente copiar todos los DLLs y pegarlos en los mismos directorios donde están ubicados los ejecutables.

## Configurar los directorios de datos de YARP

YARP necesita localizar los recursos y ficheros de configuración de RD. Para ello, crea la variable de entorno *YARP_DATA_DIRS* (ver sección anterior) y ajusta su valor a la ruta absoluta que lleva a `/share/rd` dentro del directorio de compilación o instalación de Robot Devastation.

## Problemas conocidos y observaciones

ZBar viene acompañado de una librería *zlib1.dll* obsoleta, puedes encontrar una versión más reciente entre los binarios de SDL2. Recuerda que debes omitir este archivo al copiar todos los DLL al directorio donde están ubicados los ejecutables, o mover la ruta donde se encuentra esta librería para situarla a continuación de las rutas de SDL2 en la variable de entorno *PATH*, dependiendo de tu elección en la sección anterior.

Si estás descomprimiendo todo lo relacionado con SDL2 en la misma ruta (p. ej. todas las cabeceras a un directorio `include` común, todos los DLLs a `lib`, etc.), asegúrate de dejar la versión más reciente cuando se te pregunte por elegir entre archivos con el mismo nombre. Esto se debe a otro conflicto causado por diferentes versiones de *zlib1.dll* usadas por los proyectos de SDL2 (image y ttf).

Adicionalmente, los binarios *oficiales* de ZBar han sido compilados para arquitecturas de 32 bits. Por ello, no hemos recomendado compilar en 64 bits en los pasos anteriores. Para lograrlo, puedes descargar el instalador correspondiente desde nuestro [mirror en GitHub](https://github.com/asrob-uc3m/ZBar/releases/latest).
