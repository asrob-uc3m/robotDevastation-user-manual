# Lanzar Robot Devastation - Con un robot remoto

Habiendo seguido los pasos de instalación en el PC, abrir una terminal (en Ubuntu 10.04 - 18.04 y otras distribuciones, se puede acceder a una consola a través de la combinación de las tres teclas simultáneas `CTRL` `ALT` `t`) y ejecuta (teclear y `enter`):

```bash
yarp server
```

En una nueva terminal, ejecutar:

```bash
rdServer
```

Encender robot. En otra nueva terminal, ejecutar:

```bash
robotDevastation --robotName rd2
```
