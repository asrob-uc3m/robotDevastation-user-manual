# Instalar Robot Devastation - PC \(Ubuntu\)

Estas instrucciones deberían servir para la mayoría de versiones de Ubuntu. Abre una terminal (en Ubuntu 14.04 - 18.04 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`) y ejecuta (teclear y `enter` tras cada línea, aceptando todo y entrando contraseña cuando solicitada):

```bash
cd  # va a $HOME
sudo apt install cmake cmake-curses-gui libzbar-dev libsdl2-dev libsdl2-image-dev libsdl2-mixer-dev libsdl2-ttf-dev build-essential libace-dev git
sudo apt install qtbase5-dev qtdeclarative5-dev qtmultimedia5-dev qtdeclarative5-qtquick2-plugin qtdeclarative5-window-plugin qtdeclarative5-qtmultimedia-plugin qtdeclarative5-controls-plugin qtdeclarative5-dialogs-plugin libqt5svg5
sudo apt install libjpeg8-dev  # Sólo necesario para mjpeg que acelera comunicaciones de vídeo
sudo apt install libopencv-dev  # Sólo necesario para webcam del PC
git clone https://github.com/robotology/ycm
cd ycm && mkdir build && cd build
cmake ..
make -j$(nproc)
sudo make install
cd  # go $HOME
git clone https://github.com/robotology/yarp
cd yarp && mkdir build && cd build
cmake ..
cmake .. -DCREATE_GUIS=ON  # Sólo necesario para YARP GUIs de depuración: yarpview, gyarpmanager
cmake .. -DCREATE_OPTIONAL_CARRIERS=ON -DENABLE_yarpcar_mjpeg_carrier=ON  # Sólo necesario para mjpeg que acelera comunicaciones de vídeo
cmake .. -DCREATE_DEVICE_LIBRARY_MODULES=ON -DENABLE_yarpmod_opencv_grabber=ON  # Sólo necesario para webcam del PC
make -j$(nproc) && sudo make install && sudo ldconfig
cd  # va a $HOME
git clone https://github.com/roboticslab-uc3m/color-debug
cd color-debug && mkdir build && cd build
cmake ..
make && sudo make install
cd  # go $HOME
git clone https://github.com/asrob-uc3m/yarp-devices asrob-yarp-devices
cd asrob-yarp-devices && mkdir build && cd build
cmake ..
make -j$(nproc) && sudo make install && sudo ldconfig
cd  # go $HOME
git clone https://github.com/asrob-uc3m/robotDevastation.git  # Descarga Robot Devastation
cd robotDevastation && mkdir -p build && cd build && cmake ..  # Configura Robot Devastation
make -j$(nproc)  # Compila
sudo make install  # Instala :-)
sudo ldconfig  # Por si acaso... ;-)
```
