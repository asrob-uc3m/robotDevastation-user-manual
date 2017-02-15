# Lanzar Robot Devastation - Con motores falsos y con webcam del PC

Having followed the PC installation steps, open a terminal \(on Ubuntu 10.04 - 14.10 and other distributions, a console can be accessed through the combination of the three simultaneous keys `CTRL ALT t`\) and run \(write and press `enter`\):

```bash
yarp server
```

In a new terminal, run:

```bash
rdServer
```

In another new terminal, run:

```bash
yarpdev --device FakeMotorController --name /rd2
```

In yet another new terminal, run:

```bash
robotDevastation --robotName rd2 --yarpLocalImageManager
```

This command with the experimental full-screen mode would be:

```bash
robotDevastation --robotName rd2 --yarpLocalImageManager --fullscreen
```



