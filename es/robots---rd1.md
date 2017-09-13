# RD1

![RdAmbassador front view](../assets/RD1-800px.jpg)

El robot RD1 es el de la figura. Dispone de los siguientes elementos.

-   Dos servomotores, para trucarlos para rotar más de 360º.
-   Una impresora 3D, disponible para imprimir: la estructura de soporte de los elementos y dos ruedas (cada rueda se anclará a un servomotor).
-   Un mini-PC de tipo Raspberry Pi (RPi) con una SD para el sistema operativo y software.
-   Una batería de 5 V estables para alimentar la RPi.
-   Cuatro pilas AA para alimentar los servomotores, en un portapilas.
-   Una webcam USB.
-   Un módulo wifi USB.

Trucar servomotores
-------------------

Los servomotores, de fábrica, suelen venir con límites de ejes (no pueden ir más allá de una posición en cada sentido), y se controlan en posición (poder comandar una posición deseada de una rueda). El proceso de “trucar” servomotores permite que puedan rodar sin límites y ser controlados en velocidad (poder comandar una velocidad deseada de una rueda). [Esto es un enlace a una guía externa de cómo trucar servomotores.] .

Imprimir en 3D la estructura y las ruedas
-----------------------------------------

[En este enlace están todas las piezas excepto las ruedas (ficheros STL).]

[En este enlace están las ruedas diseñadas por Obijuan que hemos utilizado.]

Ensamblaje
----------

Atornillar RPi a [rdTop] que hemos impreso. Encajar [rdSopportFront] y [rdSopportBack] que también hemos impreso. Atornillar los servomotores en los huecos que quedan. Atornillar las ruedas a los ejes de los servomotores.

Montar conexiones eléctricas RPi-servomotores
---------------------------------------------

Nosotros lo hicimos sin electrónica adicional. Conectamos:

-   Masa alimentación pilas AA &lt;-&gt; masa RPi &lt;-&gt; masa servomotor 1 &lt;-&gt; masa servomotor 2 (no importa el orden, todo conecta)
-   Tensión positiva pilas AA &lt;-&gt; terminal alimentación servomotor 1 &lt;-&gt; masa servomotor 2 (no importa el orden, todo conecta)
-   GPIO 17 &lt;-&gt; terminal señal servomotor 1 (no importa el orden, todo conecta)
-   GPIO 27 &lt;-&gt; terminal señal servomotor 2 (no importa el orden, todo conecta)

Enganchar webcam
----------------

Esto es... anclar la webcam sobre la RPi y conectar la webcam USB a la USB de la RPi!!

Instalar Raspbian en SD y rd1-software
--------------------------------------

Primero, instalar Raspbian (recomendamos 7, Weezy). [Esto es un enlace que contiene la descarga de Raspbian 7 (Wheezy).][] \[<http://www.raspberrypi.org/documentation/installation/installing-images/README.md> Esto es un enlace a cómo ca

  [Esto es un enlace a una guía externa de cómo trucar servomotores.]: http://elektronikadonbosco.blogspot.com.es/2012/08/como-trucar-servomotores-paso-paso.html
  [En este enlace están todas las piezas excepto las ruedas (ficheros STL).]: https://github.com/asrob-uc3m/robotDevastation-robots/tree/master/rd1/mechanics
  [En este enlace están las ruedas diseñadas por Obijuan que hemos utilizado.]: https://github.com/Obijuan/printbot_part_library/blob/master/wheels/Miniskybot-compatible/step-stl/Miniskybot-wheel-futaba3003-4-arms-horn-assembly.stl
  [rdTop]: https://github.com/asrob-uc3m/robotDevastation-robots/blob/master/rd1/mechanics/rdTop.stl
  [rdSopportFront]: https://github.com/asrob-uc3m/robotDevastation-robots/blob/master/rd1/mechanics/rdSopportFront.stl
  [rdSopportBack]: https://github.com/asrob-uc3m/robotDevastation-robots/blob/master/rd1/mechanics/rdSopportBack.stl
  [Esto es un enlace que contiene la descarga de Raspbian 7 (Wheezy).]: http://www.raspberrypi.org/downloads/
