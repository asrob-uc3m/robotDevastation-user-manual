# Lanzar Robot Devastation - Con Laser Tower Of Death y webcam

Habiendo seguido los pasos de instalación en el PC y Robots, y teniendo un [Laser Tower Of Death](https://github.com/asrob-uc3m/laser-tower-of-death), abrir una terminal (en Ubuntu 10.04 - 18.04 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`) y ejecuta (teclear y `enter`):

```bash
yarp server
```

En una nueva terminal, ejecutar:

```bash
rdServer
```

En otra nueva terminal, ejecutar:

```bash
yarpdev --device LaserTowerOfDeathController --name /laserTowerOfDeath
```

En otra nueva terminal más, ejecutar:

```bash
robotDevastation --robotName laserTowerOfDeath --yarpLocalImageManager
```

This command with the experimental full-screen mode would be:

```bash
robotDevastation --robotName laserTowerOfDeath --yarpLocalImageManager --fullscreen
```


