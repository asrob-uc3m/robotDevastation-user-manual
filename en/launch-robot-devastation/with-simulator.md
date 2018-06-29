# Launch Robot Devastation - With Simulator

Having followed the installation steps, and having a working [Robot Devastation simulator](https://github.com/asrob-uc3m/robotDevastation-simulator), open a terminal \(on Ubuntu 10.04 - 18.04 and other distributions, a console can be accessed through the combination of the three simultaneous keys `CTRL ALT t`\) and run \(write and press `enter`\):

```bash
yarp server
```

In a new terminal, run:

```bash
rdServer
```

In another new terminal, run:

```bash
rdSim
```

In yet another new terminal, run:

```bash
robotDevastation --robotName ecroSim
```
