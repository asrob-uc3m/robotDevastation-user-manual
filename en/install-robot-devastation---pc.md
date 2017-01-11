# Install Robot Devastation - PC

These instructions should work for most versions of Ubuntu. Open a terminal (in Ubuntu 10.04 - 16.04 and other distributions, you can access a console through the combination of the three keys `CTRL` `ALT` `t`) and execute (type `enter` after each line, Accepting everything and entering password when requested):

```bash
 sudo apt-get install cmake cmake-curses-gui libzbar-dev libsdl2-dev libsdl2-image-dev libsdl2-mixer-dev libsdl2-ttf-dev build-essential libace-dev git
 sudo apt-get install libgtkmm-2.4-dev  # Sólo necesario para YARP GUIs de depuración: yarpview, gyarpmanager
 sudo apt-get install libjpeg8-dev  # Sólo necesario para mjpeg que acelera comunicaciones de vídeo
 sudo apt-get install libopencv-dev  # Sólo necesario para webcam del PC
 git clone https://github.com/robotology/yarp
 cd yarp; mkdir build; cd build
 cmake ..
 cmake .. -DCREATE_GUIS=ON  # Sólo necesario para YARP GUIs de depuración: yarpview, gyarpmanager
 cmake .. -DCREATE_OPTIONAL_CARRIERS=ON -DENABLE_yarpcar_mjpeg_carrier=ON  # Sólo necesario para mjpeg que acelera comunicaciones de vídeo
 cmake .. -DCREATE_DEVICE_LIBRARY_MODULES=ON -DENABLE_yarpmod_opencv_grabber=ON  # Sólo necesario para webcam del PC
 make -j3 && sudo make install && sudo ldconfig && cd ../..
 git clone https://github.com/asrob-uc3m/robotDevastation.git  # Descarga Robot Devastation
 cd robotDevastation && mkdir build && cd build && cmake ..  # Configura Robot Devastation
 make  # Compila
 sudo make install  # Instala :-)
 sudo ldconfig  # Por si acaso... ;-)
```