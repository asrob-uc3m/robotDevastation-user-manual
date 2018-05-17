# Instalar Robot Devastation - Robots

Primero, instala YARP según explicado en [Instalar Robot Devastation - PC](pc-ubuntu.md).

Estas instrucciones deberían servir para la mayoría de versiones de Ubuntu. Abre una terminal (en Ubuntu 14.04 - 16.04 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`) y ejecuta (teclear y `enter` tras cada línea, aceptando todo y entrando contraseña cuando solicitada):

```bash
cd  # va a $HOME
git clone git://git.drogon.net/wiringPi # Varios dispositivos Raspi utilizan http://wiringpi.com/download-and-install/
cd wiringPi
./build # Puede requerir contraseña de sudo
cd  # va a $HOME
sudo apt install libserial-dev # Varios dispositivos dependen de libserial
git clone https://github.com/asrob-uc3m/robotDevastation-robots.git # Descarga Robot Devastation - Robots
cd robotDevastation-robots && mkdir build && cd build && cmake .. # Configura Robot Devastation - Robots
make # Compila
sudo make install # Instala :-)
sudo ldconfig # Por si acaso... ;-)
```
