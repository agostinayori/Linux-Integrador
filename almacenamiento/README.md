## 💾 Sección 4 – Almacenamiento

### 1. Agregado de Disco

Se agregó un nuevo disco virtual de 10 GB a la máquina Debian desde el entorno UTM.

### 2. Particionado

Se crearon dos particiones estándar (tipo 83) utilizando `cfdisk`:

- `/dev/sdc1` de 3 GB → Montada en `/www_dir`
- `/dev/sdc2` de 6 GB → Montada en `/backup_dir`

Ambas fueron formateadas con el sistema de archivos `ext4`:

```bash
sudo mkfs.ext4 /dev/sdc1
sudo mkfs.ext4 /dev/sdc2
```

### 3. Configuración del sitio web

- Se montó `/dev/sdc1` en `/www_dir`:
  
  ```bash
  sudo mount /dev/sdc1 /www_dir
  ```

- Se copiaron allí los archivos `index.php` y `logo.png`.

- Se modificó la configuración de Apache en el archivo:

  `/etc/apache2/sites-available/000-default.conf`

  Cambiando la línea `DocumentRoot` por:

  ```apacheconf
  DocumentRoot /www_dir
  ```

- Se reinició el servicio de Apache:

  ```bash
  sudo systemctl restart apache2
  ```

- Se ajustaron permisos y propietarios:

  ```bash
  sudo chown -R www-data:www-data /www_dir
  sudo chmod -R 755 /www_dir
  ```

### 4. Automontaje

Para que las particiones se monten automáticamente al iniciar el sistema, se editaron las entradas en el archivo `/etc/fstab`. Los `UUID` fueron obtenidos con:

```bash
sudo blkid
```

Se agregaron las siguientes líneas al final de `/etc/fstab`:

```fstab
UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx /www_dir    ext4    defaults    0    2
UUID=yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy /backup_dir ext4    defaults    0    2
```

Para comprobar que todo está bien configurado:

```bash
sudo mount -a
df -h
```

Y se verificó luego del reinicio que ambas particiones se montan automáticamente.
