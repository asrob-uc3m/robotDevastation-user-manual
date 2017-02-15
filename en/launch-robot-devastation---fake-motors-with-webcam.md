# Launch Robot Devastation - With Fake Motors And With PC Webcam

Having followed the PC y and **Robots** installation steps, open a terminal \(on Ubuntu 10.04 - 14.10 and other distributions, a console can be accessed through the combination of the three simultaneous keys `CTRL ALT t`\) and run \(write and press `enter`\):

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

This command with the experimental full-screen mode would be:

```bash
robotDevastation --robotName fakeMotors --yarpLocalImageManager --fullscreen
```



