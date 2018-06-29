# Launch Robot Devastation - With Fake Motors And With PC Webcam

Having followed the installation steps, open a terminal (on Ubuntu 10.04 - 18.10 and other distributions, a console can be accessed through the combination of the three simultaneous keys `CTRL ALT t`) and run (write and press `enter`):

```bash
yarp server
```

In a new terminal, run:

```bash
rdServer
```

In another new terminal, run:

```bash
yarpdev --device FakeMotorController --name /fakeMotors
```

In yet another new terminal, run:

```bash
robotDevastation --robotName fakeMotors --yarpLocalImageManager
```
