# Cómo crear un servicio systemd para ejecutar un script

## Requisitos

- Un sistema operativo Linux
- Acceso de root

## Pasos


1. Cree un directorio para el servicio:

```
sudo mkdir /etc/systemd/system/hola_mundo.service

```
2. Cree el archivo de unidad de servicio:
```
sudo nano /etc/systemd/system/hola_mundo.service
```
Agregue el siguiente contenido al archivo:
```
[Unit]
Description=Hola Mundo Service

[Service]
Type=simple
ExecStart=/bin/bash /etc/systemd/system/hola_mundo.sh

[Install]
WantedBy=multi-user.target
```
En este archivo, estamos definiendo los siguientes parámetros:

- Description: Una breve descripción del servicio.
- Type: El tipo de servicio. En este caso, estamos usando el tipo simple, que significa que el servicio se ejecutará como un proceso único.
- ExecStart: El comando que se ejecutará cuando se inicie el servicio. En este caso, estamos ejecutando el script /etc/systemd/system/hola_mundo.sh.
- WantedBy: El objetivo que debe estar activo cuando el servicio se inicie. En este caso, queremos que el servicio se inicie cuando el sistema esté listo para usar, por lo que estamos usando el objetivo multi-user.target.

3. Cree el script de shell:
```
sudo nano /etc/systemd/system/hola_mundo.sh
```
Agregue el siguiente contenido al script:
```
#!/bin/bash

echo "Hola mundo! La fecha actual es $(date)"

```
Este script simplemente imprime un saludo y la fecha actual.

4. Habilite el servicio:
```
sudo systemctl enable hola_mundo
```

5. Arranque el servicio:
```
sudo systemctl start hola_mundo
```
Para verificar que el servicio está funcionando, use el siguiente comando:
```
sudo systemctl status hola_mundo
```

La salida del comando debe ser similar a la siguiente:
```
● hola_mundo.service - Hola Mundo Service
     Loaded: loaded (/etc/systemd/system/hola_mundo.service; enabled; vendor preset: enabled)
     Active: active (running) since Thu 2023-07-21 10:50:10 EDT; 1min 10s ago
       Docs: man:systemd-units(5)
   Main PID: 1234 (hola_mundo)
      Tasks: 1 (limit: 512)
     Memory: 100 KiB
      CPU: 2ms
     CGroup: /system.slice/hola_mundo.service
          └─1234 /bin/bash /etc/systemd/system/hola_mundo.sh

Jul 21 10:50:10 my_computer systemd[1]: Starting Hola Mundo Service...
Jul 21 10:50:10 my_computer systemd[1]: Started Hola Mundo Service.
```