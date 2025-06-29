# 🧩 Sección 2 – Configuración de servicios (SSH, WEB y Base de Datos)

## 🔐 1. SSH

Se instaló y configuró el servicio de SSH en el servidor Debian, permitiendo el acceso remoto como `root` desde una máquina física (en este caso, mi Mac) utilizando autenticación por **clave pública/privada**, tal como indicaba la consigna.  
La clave privada fue provista en Blackboard, y se colocó la clave pública en `/root/.ssh/authorized_keys`.

Se editaron las siguientes líneas en `/etc/ssh/sshd_config`:

```bash
PermitRootLogin yes
PubkeyAuthentication yes
AuthorizedKeysFile .ssh/authorized_keys
PasswordAuthentication no
```

Luego se reinició el servicio con:

```bash
sudo systemctl restart ssh
```

Las pruebas de conectividad fueron realizadas correctamente desde la terminal de mi Mac, sin necesidad de ingresar contraseña.

---

## 🌐 2. Servidor WEB (Apache + PHP)

Se instaló Apache con soporte para PHP:

```bash
sudo apt install apache2 php libapache2-mod-php
```

Posteriormente se verificó que Apache estuviera corriendo correctamente con:

```bash
systemctl status apache2
```

Los archivos `index.php` y `logo.png` (provistos en Blackboard) se copiaron al directorio por defecto `/var/www/html/`.  
Para probar el funcionamiento, se accedió desde una máquina externa (mi Mac) con:

```bash
curl http://192.168.0.42/index.php
```

y se confirmó que el archivo PHP era interpretado correctamente por el servidor.

> ⚠️ **Nota:**  
> Fue necesario instalar también el módulo de PHP para MySQL:

```bash
sudo apt install php7.4-mysql
```

porque sin eso PHP no podía conectarse a la base de datos y arrojaba un error fatal relacionado con la clase `mysqli`.

---

## 🛢️ 3. Base de datos (MariaDB)

Se instaló MariaDB con:

```bash
sudo apt install mariadb-server
```

Luego se importó correctamente el archivo `db.sql` con el siguiente comando:

```bash
sudo mariadb < /root/db.sql
```

La base de datos `ingenieria` fue creada automáticamente por el script.  
Se verificó el contenido mediante consultas desde la consola de MariaDB, y se confirmó que las tablas estaban correctamente cargadas.

Finalmente, se modificó el archivo `index.php` para establecer correctamente la conexión con la base de datos, y se mostraron los datos esperados al acceder al sitio desde otra máquina.
