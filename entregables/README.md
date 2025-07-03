## 📦 Paso 6: Entregables

En esta sección se prepararon todos los archivos requeridos para la entrega final del TP integrador, cumpliendo con las consignas específicas de compresión y estructura.

---

### ✅ Archivos comprimidos

Se comprimieron individualmente los siguientes directorios del sistema en formato `.tar.gz`:

- `/etc` → `etc.tar.gz`
- `/opt` → `opt.tar.gz`
- `/root` → `root.tar.gz`
- `/www_dir` → `www_dir.tar.gz`
- `/backup_dir` → `backup_dir.tar.gz`

Todos los archivos se generaron con el comando:

> tar -czvf NOMBRE.tar.gz /ruta

Por ejemplo:

> tar -czvf etc.tar.gz /etc

---

### 🔸 División del directorio `/var`

El archivo `var.tar.gz` pesaba más de 50 MB, por lo que fue necesario dividirlo en partes más pequeñas para subirlo a GitHub. Se usó el siguiente comando:

> split -b 50M var.tar.gz var.tar.gz.part_

Esto generó los archivos:

- `var.tar.gz.part_aa`
- `var.tar.gz.part_ab`

---

### 🛠️ Agrupación y transferencia

Para facilitar el traslado, se agruparon todos los `.tar.gz` y partes del `/var` en un único archivo:

> tar -czvf entregables.tar.gz etc.tar.gz opt.tar.gz root.tar.gz www_dir.tar.gz backup_dir.tar.gz var.tar.gz.part_*

Luego, se transfirió este archivo desde la VM a mi Mac:

> scp -i ~/.ssh/clave_tp root@192.168.0.42:/tmp/entregables.tar.gz ~/Documents/

Y se descomprimió localmente dentro de la carpeta del proyecto:

> tar -xzvf ~/Documents/entregables.tar.gz -C ~/Documents/GitHub/Linux-Integrador/entregables

---

### Subida a GitHub

Desde el directorio raíz del repositorio local, se subieron todos los archivos comprimidos con:

> git add .  
> git commit -m "Subo entregables comprimidos del TP"  
> git push origin main
