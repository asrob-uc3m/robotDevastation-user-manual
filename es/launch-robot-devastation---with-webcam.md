# Lanzar Robot Devastation - Sin robot y con webcam del PC

Habiendo seguido los pasos de instalación en el PC, abrir una terminal \(en Ubuntu 10.04 - 16.04 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`\) y ejecuta \(teclear y `enter`\):

```bash
yarp server
```

En una nueva terminal, ejecutar:

```bash
rdServer
```

En otra nueva terminal, ejecutar:

```bash
robotDevastation --mockupRobotManager --yarpLocalImageManager
```

Este comando con el modo experimental a pantalla completa sería:

```bash
robotDevastation --mockupRobotManager --yarpLocalImageManager --fullscreen
```



