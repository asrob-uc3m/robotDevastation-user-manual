# RD2

![RD2-800px.jpg](../../assets/RD2-800px.jpg)

El robot RD2 es el de la figura. Dispone de los siguientes elementos.
(Actualizar lista de componentes)

  - Dos servomotores, para trucarlos para rotar más de 360º
    [(Servo)](http://www.banggood.com/es/TowerPro-MG995-Metal-Servo-p-73885.html)
  - Una impresora 3D, disponible para imprimir: la estructura de soporte
    de los elementos y dos ruedas (cada rueda se anclará a un
    servomotor).
  - Juntas tóricas de 6 cm (se compran en ferretería) para las ruedas o
    similar.
  - Bola (rueda loca, estilo [Pololu Ball Caster with 1/2" Metal
    Ball](https://www.pololu.com/product/953)).
  - Un mini-PC de tipo Raspberry Pi (RPi) con una SD de 8 GiB (o más)
    para el sistema operativo y software.
  - Una batería de 5 V estables para alimentar la RPi. Se recomienda
    usar batería para movil [(Enlace
    Bateria)](http://www.banggood.com/es/2600mAh-Portable-Mobile-Power-Bank-For-Samsung-Galaxy-S4-I9500-p-74819.html)
  - Bateria LiPo 7.2V 1000mAh [(Enlace bateria
    LiPo)](http://www.banggood.com/es/WLtoys-V912-V915-Upgraded-Battery-7_4V-1000mAh-25C--p-71191.html)
    y cargador de LiPo().
  - Conectores para la bateria ().
  - Una webcam USB
    (http://www.banggood.com/Wholesale-Fashion-USB-2\_0-Webcam-30M-PC-Camera-HD-Camera-Web-Cam-For-PC-Laptop-Computer-p-49628.html).
  - Un módulo wifi USB.
  - Reguladores
  - Placa de puntos... puede ser necesario soldador\!

## Trucar servomotores

Los servomotores, de fábrica, suelen venir con límites de ejes (no
pueden ir más allá de una posición en cada sentido), y se controlan en
posición (poder comandar una posición deseada de una rueda). El proceso
de "trucar" servomotores permite que puedan rodar sin límites y ser
controlados en velocidad (poder comandar una velocidad deseada de una
rueda). [Cómo trucar
servomotores](http://elektronikadonbosco.blogspot.com.es/2012/08/como-trucar-servomotores-paso-paso.html).

## Imprimir en 3D la estructura y las ruedas

[Ficheros de todas las piezas
(STL)](https://github.com/asrob-uc3m/robotDevastation-robots/tree/master/rd2/mechanics).

## Montar conexiones eléctricas RPi-servomotores

Nosotros lo hicimos sin electrónica adicional. Conectamos:

  - Masa alimentación pilas AA \<-\> masa RPi \<-\> masa servomotor 1
    \<-\> masa servomotor 2 (no importa el orden, todo conecta)
  - Tensión positiva pilas AA \<-\> terminal alimentación servomotor 1
    \<-\> terminal alimentación servomotor 2 (no importa el orden, todo
    conecta)
  - GPIO 17 \<-\> terminal señal servomotor 1 (no importa el orden, todo
    conecta)
  - GPIO 27 \<-\> terminal señal servomotor 2 (no importa el orden, todo
    conecta)

## Enganchar webcam

Esto es... anclar la webcam sobre la RPi y conectar la webcam USB a la
USB de la RPi\!\!

## Crear SD con Raspbian y robotDevastation-robots/raspi software

Descargar imagen (ocupa entre 7.0 y 8.0
GiB):

`wget `<http://asrob.uc3m.es/robotDevastation-robots/2015-05-05-raspbian-wheezy-rd.img>

Volcar imagen a SD de 8.0 GiB o más:

`sudo dd bs=4M if=2015-05-05-raspbian-wheezy-rd.img of=/dev/mmcblk0`

Esto sería el nivel básico. Si esto no te llega, aquí tienes: [Crear SD
con Raspbian y robotDevastation-robots/raspi software (avanzado: de
cero)](Crear_SD_con_Raspbian_y_robotDevastation-robots/raspi_software_\(avanzado:_de_cero\) "wikilink").
