# Launch Robot Devastation - With Laser Tower Of Death And PC Webcam

Having followed the PC and Robots installation steps, and having a [Laser Tower Of Death](https://github.com/asrob-uc3m/laser-tower-of-death), open a terminal (on Ubuntu 10.04 - 18.04 and other distributions, a console can be accessed through the combination of the three simultaneous keys `CTRL ALT t`) and run (write and press `enter`):

```bash
yarp server
```

In a new terminal, run:

```bash
rdServer
```

In another new terminal, run:

```bash
yarpdev --device LaserTowerOfDeathController --name /laserTowerOfDeath
```

In yet another new terminal, run:

```bash
robotDevastation --robotName laserTowerOfDeath --yarpLocalImageManager
```
