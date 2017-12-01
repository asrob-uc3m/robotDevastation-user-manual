# Install Robot Devastation - Robots

Assumes you have previously done [Install Robot Devastation - PC](install-robot-devastation-ubuntu---pc.md).

These instructions should work for most versions of Ubuntu. Open a terminal (in Ubuntu 10.04 - 16.04 and other distributions, you can access a console through the combination of the three keys `CTRL` `ALT` `t`) and execute (type `enter` after each line, Accepting everything and entering password when requested):

Install robotDevastation-robots
```bash
cd  # go $HOME
git clone git://git.drogon.net/wiringPi # For Raspi modules (default to activated)
cd wiringPi
./build
cd  # go $HOME
sudo apt-get install libserial-dev libboost-all-dev # For LaserTowerOfDeathController
git clone https://github.com/asrob-uc3m/robotDevastation-robots.git # Download Robot Devastation - Robots
cd robotDevastation-robots && mkdir build && cd build && cmake .. # Configure Robot Devastation - Robots
make # Compile
sudo make install # Install :-)
sudo ldconfig # Just in case... ;-)
```

    Note: you can find Wiring Pi website (for Rd Ambassador) here: http://wiringpi.com/download-and-install/