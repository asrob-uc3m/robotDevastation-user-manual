# Install Robot Devastation - Robots

These instructions should work for most versions of Ubuntu. Open a terminal (in Ubuntu 10.04 - 16.04 and other distributions, you can access a console through the combination of the three keys `CTRL` `ALT` `t`) and execute (type `enter` after each line, Accepting everything and entering password when requested):

```bash
git clone https://github.com/asrob-uc3m/robotDevastation-robots.git # Descarga Robot Devastation - Robots
cd robotDevastation-robots && mkdir build && cd build && cmake .. # Configura Robot Devastation - Robots
make # Compila
sudo make install # Instala :-)
sudo ldconfig # Por si acaso... ;-)
```

