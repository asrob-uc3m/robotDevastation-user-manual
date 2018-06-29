# Lanzar Robot Devastation - Con Simulador

Habiendo seguido los pasos de instalación, y teniendo un [Robot Devastation simulator](https://github.com/asrob-uc3m/robotDevastation-simulator) funcional, abrir una terminal (en Ubuntu 10.04 - 18.04 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`) y ejecuta (teclear y `enter`):

```bash
yarp server
```

En una nueva terminal, ejecutar:

```bash
rdServer
```

En otra nueva terminal, ejecutar:

```bash
rdSim
```

En otra nueva terminal más, ejecutar:

```bash
robotDevastation --robotName ecroSim
```
