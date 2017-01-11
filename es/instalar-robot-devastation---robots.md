# Instalar Robot Devastation - Robots

Estas instrucciones deberían servir para la mayoría de versiones de Ubuntu. Abre una terminal (en Ubuntu 10.04 - 14.10 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`) y ejecuta (teclear y `enter` tras cada línea, aceptando todo y entrando contraseña cuando solicitada):
```bash
git clone https://github.com/asrob-uc3m/robotDevastation-robots.git # Descarga Robot Devastation - Robots
cd robotDevastation-robots && mkdir build && cd build && cmake .. # Configura Robot Devastation - Robots
make # Compila
sudo make install # Instala :-)
sudo ldconfig # Por si acaso... ;-)
```