# Lanzar Robot Devastation - Con motores falsos y con webcam del PC

Habiendo seguido los pasos de instalación en el PC y **Robots**, abrir una terminal (en Ubuntu 10.04 - 18.04 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`) y ejecuta (teclear y `enter`):

```bash
yarp server
```

En una nueva terminal, ejecutar:

```bash
rdServer
```

En otra nueva terminal, ejecutar:

```bash
yarpdev --device FakeMotorController --name /fakeMotors
```

En otra nueva terminal más, ejecutar:

```bash
robotDevastation --robotName fakeMotors --yarpLocalImageManager
```

This command with the experimental full-screen mode would be:

```bash
robotDevastation --robotName fakeMotors --yarpLocalImageManager --fullscreen
```
