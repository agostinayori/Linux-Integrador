# Linux-Integrador

# TP Integrador – Computación Aplicada

## 🧾 Descripción general

Este proyecto consiste en la configuración y administración de un servidor GNU/Linux Debian en una máquina virtual que nos da la Universidad, con el objetivo de aplicar los conocimientos adquiridos sobre servicios, red, almacenamiento, usuarios, permisos y automatización.

Cada sección del trabajo esta organizada por carpetas temáticas para facilitar la colaboración en grupo y el seguimiento por parte de los docentes.

---

## 🛠️ Integrantes del grupo

- Agostina Yori 
- Fausto Villalba
- Oscar Agustin Cabral

---

## 📁 Estructura del repositorio

| Carpeta | Contenido |
|--------|-----------|
| `configuracion-entorno/` | Cambio de contraseña, hostname, y configuración inicial del sistema |
| `servicios/apache/` | Instalación y configuración del servidor web Apache con soporte PHP |
| `servicios/ssh/` | Configuración del acceso por SSH con clave pública/privada |
| `servicios/mariadb/` | Instalación y carga de la base de datos MariaDB |
| `red/` | Configuración de red con IP estática (ADDRESS, NETMASK, GATEWAY) |
| `almacenamiento/particion/` | Creación y montaje de particiones para `/www_dir` y `/backup_dir` |
| `almacenamiento/apache-config/` | Modificación de Apache para servir desde `/www_dir` |
| `backup/` | Script de backup (`backup_full.sh`) y programación en cron |
| `entregables/` | Archivos comprimidos (.tar.gz) con el contenido solicitado y el diagrama topológico |

---

## 🚀 Objetivos principales

- Gestionar usuarios, grupos y permisos con buenas prácticas de administración.
- Instalar y configurar servicios esenciales de red y almacenamiento.
- Automatizar backups usando scripts y tareas programadas.
- Documentar la infraestructura implementada de forma clara y accesible.

---

## 📌 Notas

- Este repositorio fue creado para centralizar todo el trabajo práctico.
- Las contribuciones de cada integrante se van a ir registrando por carpeta o commits individuales.
- El trabajo será defendido en una presentación oral.

---
