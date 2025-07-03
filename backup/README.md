# Paso 5: Backup

En esta sección se desarrolló un script de backup completo, automatizado y parametrizable, cumpliendo con todos los requisitos de la consigna.

---

## 📂 Estructura general

- Script ubicado en: `/opt/scripts/backup_full.sh`
- Backups generados en: `/backup_dir`
- Directorios de origen: definidos por argumentos (ej. `/var/log`, `/www_dir`)
- Automatización mediante `cron`

---

## 🧠 Funcionalidad del script

El script `backup_full.sh` permite realizar copias comprimidas (`.tar.gz`) de cualquier directorio del sistema, guardándolas en una ubicación destino y utilizando como nombre de archivo el formato ANSI de fecha (YYYYMMDD).

---

## 🔹 Parámetros

- **Origen:** Ruta del directorio a respaldar  
- **Destino:** Ruta donde guardar el archivo `.tar.gz`

---

## 📝 Ejemplo de uso

    /opt/scripts/backup_full.sh /var/log /backup_dir

Este comando generará un archivo con nombre como:

    /backup_dir/log_bkp_20250703.tar.gz

---

## ❓ Opción de ayuda

Al ejecutar:

    /opt/scripts/backup_full.sh -help

Se mostrará una breve guía con la sintaxis esperada y una descripción de los argumentos requeridos.

---

## 🔍 Validaciones del script

Antes de crear el backup, el script verifica que:

- El directorio de origen exista.
- El directorio de destino esté montado correctamente.

Si algo falla, el script se detiene y muestra un mensaje de error.

---

## ⏱ Automatización con `cron`

El script fue agendado en el `crontab` con estas dos tareas:

**Todos los días a las 00:00 — Backup de `/var/log`:**

    0 0 * * * /opt/scripts/backup_full.sh /var/log /backup_dir

**Lunes, miércoles y viernes a las 23:00 — Backup de `/www_dir`:**

    0 23 * * 1,3,5 /opt/scripts/backup_full.sh /www_dir /backup_dir

---

## ✅ Pruebas realizadas

- El script genera backups correctamente al ejecutarse manualmente.
- Los archivos aparecen en `/backup_dir` con nombres adecuados.
- El contenido se puede listar con `tar -tzf archivo.tar.gz`.
- Las tareas en `cron` se registraron correctamente.
