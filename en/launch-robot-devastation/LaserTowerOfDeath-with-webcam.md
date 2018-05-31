# Launch Robot Devastation - With LaserTowerOfDeath And PC Webcam

Having followed the PC and Robots installation steps, and having a [LaserTowerOfDeath](https://github.com/asrob-uc3m/robotDevastation-robots/tree/develop/laserTowerOfDeath), open a terminal \(on Ubuntu 10.04 - 14.10 and other distributions, a console can be accessed through the combination of the three simultaneous keys `CTRL ALT t`\) and run \(write and press `enter`\):

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

This command with the experimental full-screen mode would be:

```bash
robotDevastation --robotName laserTowerOfDeath --yarpLocalImageManager --fullscreen
```



