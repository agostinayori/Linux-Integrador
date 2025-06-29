## 3. Configuración de Red

Para cumplir con esta sección, se configuró la interfaz de red de la máquina virtual con una IP estática. Esto se hizo editando el archivo `/etc/network/interfaces` con los siguientes valores:

```bash
auto enp0s1
iface enp0s1 inet static
    address 192.168.0.42
    netmask 255.255.255.0
    gateway 192.168.0.1
```

Luego, se reinició el servicio de red con:

```bash
sudo systemctl restart networking
```

Se verificó que la IP fue asignada correctamente con:

```bash
ip a
```

Y también que la puerta de enlace estuviera configurada con:

```bash
ip route
```

---

📌 La IP `192.168.0.42` se encuentra en el mismo rango que la máquina física.  
📌 El archivo incluye los campos `ADDRESS`, `NETMASK` y `GATEWAY`, como exige la consigna.  
📌 La interfaz configurada (`enp0s1`) corresponde con la detectada por el sistema.

