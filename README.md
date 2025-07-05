# Linux-Integrador

# TP Integrador – Computación Aplicada

## 🧾 Descripción general

Este proyecto consiste en la configuración y administración de un servidor GNU/Linux Debian en una máquina virtual que nos da la UP, con el objetivo de aplicar los conocimientos adquiridos sobre servicios, red, almacenamiento, usuarios, permisos y automatización.

---

## 📁 Estructura del repo

| Carpeta | Contenido |
|--------|-----------|
| `configuracion-entorno/` | Cambio de contraseña, hostname, y configuración inicial del sistema |
| `servicios/` | Instalación y configuración del servidor web Apache con soporte PHP, Configuración del acceso por SSH con clave pública/privada, Instalación y carga de la base de datos MariaDB |
| `red/` | Configuración de red con IP estática (ADDRESS, NETMASK, GATEWAY) |
| `almacenamiento/` | Creación y montaje de particiones para `/www_dir` y `/backup_dir`, Modificación de Apache para servir desde `/www_dir` |
| `backup/` | Script de backup (`backup_full.sh`) y programación en cron |
| `entregables/` | Archivos comprimidos (.tar.gz) con el contenido solicitado y el diagrama topológico |

---

## 🚀 Objetivos principales

- Gestionar usuarios, grupos y permisos con buenas prácticas de administración.
- Instalar y configurar servicios esenciales de red y almacenamiento.
- Automatizar backups usando scripts y tareas programadas.
- Documentar la infraestructura implementada de forma clara y accesible.

