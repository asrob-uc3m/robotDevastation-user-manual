# Install Robot Devastation - PC

These instructions should work for most versions of Ubuntu. Open a terminal (in Ubuntu 10.04 - 16.04 and other distributions, you can access a console through the combination of the three keys `CTRL` `ALT` `t`) and execute (type `enter` after each line, Accepting everything and entering password when requested):

```bash
cd  # go $HOME
sudo apt-get update # update the apt-get database
sudo apt-get install cmake cmake-curses-gui libzbar-dev libsdl2-dev libsdl2-image-dev libsdl2-mixer-dev libsdl2-ttf-dev build-essential libace-dev git
sudo apt-get install libgtkmm-2.4-dev  # Only required for YARP debug GUIs: yarpview, gyarpmanager
sudo apt-get install qtbase5-dev qtdeclarative5-dev qtmultimedia5-dev qtdeclarative5-qtquick2-plugin qtdeclarative5-window-plugin qtdeclarative5-qtmultimedia-plugin qtdeclarative5-controls-plugin qtdeclarative5-dialogs-plugin libqt5svg5
sudo apt-get install libjpeg8-dev  # Only required for mjpeg that should improve video comms
sudo apt-get install libopencv-dev  # Only required for PC webcam
git clone https://github.com/robotology/yarp
cd yarp; mkdir build; cd build
cmake ..
cmake .. -DCREATE_GUIS=ON  # Only required for YARP debug GUIs: yarpview, gyarpmanager
cmake .. -DCREATE_OPTIONAL_CARRIERS=ON -DENABLE_yarpcar_mjpeg_carrier=ON  # Only required for mjpeg that should improve video comms
cmake .. -DCREATE_DEVICE_LIBRARY_MODULES=ON -DENABLE_yarpmod_opencv_grabber=ON  # Only required for PC webcam
make -j3 && sudo make install && sudo ldconfig && cd ../..
git clone https://github.com/asrob-uc3m/robotDevastation.git  # Download Robot Devastation
cd robotDevastation && mkdir build && cd build && cmake ..  # Configure Robot Devastation
make  # Compile
sudo make install  # Install :-)
sudo ldconfig  # Just in case... ;-)
```