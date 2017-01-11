# Without Any Robot And With Webcam

Having followed the PC installation steps, open a terminal (on Ubuntu 10.04 - 14.10 and other distributions, a console can be accessed through the combination of the three simultaneous keys `CTRL ALT t`) and run (write and press `enter`):

```bash
yarp server
```

In a new terminal, run:

```bash
rdServer
```

In another new terminal, run:

```bash
robotDevastation --mockupRobotManager --yarpLocalImageManager
```

This command with the experimental full-screen mode would be:

```bash
robotDevastation --mockupRobotManager --yarpLocalImageManager --fullscreen
```
