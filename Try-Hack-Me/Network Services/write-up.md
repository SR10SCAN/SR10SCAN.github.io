
# Explotación de Servicios (SMB, SSH, FTP y Telnet)

Este documento detalla el proceso de intrusión y obtención de banderas en un entorno de laboratorio, cubriendo desde la enumeración de red hasta la ejecución de una **Reverse Shell**.

---

## 1. Fase de Reconocimiento y SMB

El primer paso consistió en identificar la superficie de ataque y los recursos compartidos disponibles en la red para establecer un punto de entrada.

### Enumeración de SMB
Utilizamos herramientas como `enum4linux` y `nxc` (NetExec) para identificar grupos de usuarios, la versión del sistema operativo y el nombre de la máquina objetivo.

**Comando ejecutado:**
```bash
enum4linux -a 10.66.134.66
```

![Evidencia de Enumeración](image.png)
###información del sistema operativo
