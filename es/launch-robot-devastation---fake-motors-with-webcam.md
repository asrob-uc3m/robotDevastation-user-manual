# Lanzar Robot Devastation - Con motores falsos y con webcam del PC

Habiendo seguido los pasos de instalación en el PC, abrir una terminal \(en Ubuntu 10.04 - 16.04 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`\) y ejecuta \(teclear y `enter`\):

```bash
yarp server
```

En una nueva terminal, ejecutar:

```bash
rdServer
```

En otra nueva terminal, ejecutarn:

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



