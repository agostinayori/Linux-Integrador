## Parte 1 – Configuración del entorno base

### 🎯 Objetivo
Dejar el sistema operativo Debian funcional en la VM para comenzar el trabajo de administración.

---

## ✅ Pasos realizados:

### 1. Levanté la VM con archivos ".qcow2":
- Usé UTM para crear una nueva máquina virtual en modo "Emulate" (no "Virtualize").
- No seleccioné ninguna imagen ISO; elegí "Boot: ninguno" al crearla.
- Asigné los discos "TPVMCA-disk1.qcow2" (booteable) y `TPVMCA-disk2.qcow2` (contiene /home).

### 2. Accedí como root por primera vez:
- Ingresé sin contraseña inicial.
- Monté el sistema con permisos de escritura desde el GRUB.
- Blanqueé y cambié la contraseña de root a: `palermo`.

### 3. Cambié el hostname del sistema:
- Ejecuté: `hostnamectl set-hostname TPServer`

### 4. Configuré el teclado:
- El layout estaba desordenado, no coincidía con mi teclado físico (US).
- Usé: "dpkg-reconfigure keyboard-configuration"
- Seleccioné: "Generic 105-key PC" → `English (US)`
- Verifiqué y reinicié.


