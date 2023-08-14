### Bitácora de comandos de Sistemas Operativos


## Comandos 

### Ejecución de Scripts Python

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| python3 SO_S04_02_sumatoria_Simple.py | Ejecutar un script Python | `python3 SO_S04_02_sumatoria_Simple.py` |
| python3 SO_S04_03_sumatoria_Hilos.py | Ejecutar un script Python | `python3 SO_S04_03_sumatoria_Hilos.py` |
| python3 SO_S04_04_sumatoria_MuchosHilos.py | Ejecutar un script Python | `python3 SO_S04_04_sumatoria_MuchosHilos.py` |
| python3 SO_S04_05_sumatoria_Procesos.py | Ejecutar un script Python | `python3 SO_S04_05_sumatoria_Procesos.py` |

### Comandos de Administración del Sistema

#### Actualización y Mantenimiento

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| sudo apt update | Actualizar la lista de paquetes disponibles | `sudo apt update` |
| sudo apt upgrade | Actualizar paquetes instalados | `sudo apt upgrade` |

#### Servidor Web Apache2

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| sudo apt install apache2 | Instalar el servidor web Apache2 | `sudo apt install apache2` |
| sudo chmod 777 -R * | Cambiar permisos de archivos y directorios | `sudo chmod 777 -R *` |
| sudo mkdir prueba | Crear un directorio | `sudo mkdir prueba` |

#### Información del Sistema

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| sudo dmidecode --type 17 | Mostrar información del sistema | `sudo dmidecode --type 17` |
| free -h | Mostrar información de memoria | `free -h` |
| swapon | Activar particiones de intercambio | `swapon` |
| cat /proc/sys/vm/swappiness | Mostrar valor de swappiness | `cat /proc/sys/vm/swappiness` |
| sudo sysctl vm.swappiness=45 | Cambiar valor de swappiness | `sudo sysctl vm.swappiness=45` |
| sudo mkdir /mnt/ram_disk | Crear un directorio en RAM | `sudo mkdir /mnt/ram_disk` |
| sudo mount -t tmpfs -o size=1024m new_ram_disk /mnt/ram_disk | Montar un sistema de archivos en RAM | `sudo mount -t tmpfs -o size=1024m new_ram_disk /mnt/ram_disk` |

#### Docker

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" | Agregar repositorio de Docker | `sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"` |
| sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose | Instalar Docker y herramientas relacionadas | `sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose` |
| sudo usermod -aG docker ${USER} | Agregar usuario al grupo "docker" | `sudo usermod -aG docker ${USER}` |
| sudo systemctl start docker | Iniciar el servicio Docker | `sudo systemctl start docker` |
| sudo systemctl enable docker | Habilitar el inicio automático de Docker | `sudo systemctl enable docker` |
| sudo docker run hello-world | Ejecutar un contenedor Docker | `sudo docker run hello-world` |
| docker search ubuntu | Buscar imágenes Docker | `docker search ubuntu` |
| docker pull ubuntu | Descargar una imagen Docker | `docker pull ubuntu` |
| docker images | Listar imágenes Docker | `docker images` |
| docker run ubuntu | Ejecutar una imagen Docker | `docker run ubuntu` |
| sudo docker ps -a | Listar contenedores Docker | `sudo docker ps -a` |
| sudo docker start d9b100f2f636 | Iniciar un contenedor Docker específico | `sudo docker start d9b100f2f636` |
| sudo docker stop d9b100f2f636 | Detener un contenedor Docker específico | `sudo docker stop d9b100f2f636` |
| docker rmi Image Image | Eliminar imágenes Docker | `docker rmi Image Image` |
| docker rm ID | Eliminar un contenedor Docker por ID | `docker rm ID` |
| docker run --rm image_name | Ejecutar una imagen y eliminar después | `docker run --rm image_name` |
| sudo docker rm $(sudo docker ps -a -f status=exited -q) | Eliminar contenedores detenidos | `sudo docker rm $(sudo docker ps -a -f status=exited -q)` |
| sudo docker run -it ubuntu | Ejecutar un contenedor interactivo Ubuntu | `sudo docker run -it ubuntu` |
| docker commit -m "Paquetes actualizados" -a "Mortasoft" 9a3d54ec6631 usuario_dockerhub/ubuntu | Crear una nueva imagen a partir de un contenedor | `docker commit -m "Paquetes actualizados" -a "Mortasoft" 9a3d54ec6631 usuario_dockerhub/ubuntu` |
| sudo docker login -u usuario_dockerhub | Iniciar sesión en Docker Hub | `sudo docker login -u usuario_dockerhub` |
| sudo docker commit b7dc036f2c99 | Crear una nueva imagen a partir de un contenedor | `sudo docker commit b7dc036f2c99` |
| sudo docker push docker-registry-username/docker-image-name | Subir una imagen a Docker Hub | `sudo docker push docker-registry-username/docker-image-name` |
| sudo docker run -it -p 9090:80 --name mi_ubuntu ubuntu | Ejecutar contenedor con puertos mapeados | `sudo docker run -it -p 9090:80 --name mi_ubuntu ubuntu` |

### Comandos en Contenedores

#### Dentro del Contenedor

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| apt update | Actualizar lista de paquetes (dentro del contenedor) | `apt update` |
| apt install apache2 | Instalar Apache2 (dentro del contenedor) | `apt install apache2` |
| apt install nano | Instalar el editor de texto Nano (dentro del contenedor) | `apt install nano` |
| service apache2 start | Iniciar el servicio Apache2 (dentro del contenedor) | `service apache2 start` |
| echo 'Hola Mundo' > /var/www/html/index.html | Crear un archivo de texto (dentro del contenedor) | `echo 'Hola Mundo' > /var/www/html/index.html` |

### Gestión de Contenedores con Docker

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| docker pull portainer/portainer-ce:latest | Descargar la imagen de Portainer | `docker pull portainer/portainer-ce:latest` |
| sudo docker run -d -p 8000:8000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest | Ejecutar Portainer como contenedor Docker | `sudo docker run -d -p 8000:8000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest` |
| sudo docker stop portainer | Detener el contenedor Portainer | `sudo docker stop portainer` |
| sudo docker rm portainer | Eliminar el contenedor Portainer | `sudo docker rm portainer` |
| sudo docker rm volume portainer | Eliminar volumen asociado a Portainer | `sudo docker rm volume portainer` |

### Comandos de Administración del Sistema (Continuación)

#### Administración de Archivos y Directorios

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| ls | Listar archivos y directorios en el directorio actual | `ls` |
| ls -l | Listar archivos y directorios con detalles | `ls -l` |
| cd | Cambiar de directorio | `cd /ruta/del/directorio` |
| pwd | Mostrar la ruta del directorio actual | `pwd` |
| mkdir | Crear un directorio | `mkdir nombre_del_directorio` |
| rmdir | Eliminar un directorio vacío | `rmdir nombre_del_directorio` |
| touch | Crear un archivo vacío | `touch nombre_del_archivo` |
| rm | Eliminar archivos o directorios | `rm nombre_del_archivo` o `rm -r nombre_del_directorio` |
| cp | Copiar archivos o directorios | `cp archivo_origen archivo_destino` o `cp -r directorio_origen directorio_destino` |
| mv | Mover o renombrar archivos o directorios | `mv archivo_origen archivo_destino` o `mv archivo_origen nuevo_nombre` |

### Comandos de Administración del Sistema (Continuación)

#### Administración de Archivos y Directorios (Continuación)

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| cat | Mostrar el contenido de un archivo | `cat nombre_del_archivo` |
| less | Mostrar el contenido de un archivo de forma interactiva | `less nombre_del_archivo` |
| nano | Abrir el editor de texto Nano | `nano nombre_del_archivo` |
| grep | Buscar patrones en archivos | `grep "patron" archivo` |
| ps | Mostrar procesos en ejecución | `ps` |
| top | Mostrar información en tiempo real de procesos | `top` |
| htop | Versión mejorada de `top` | `htop` |
| kill | Finalizar procesos por su ID o nombre | `kill PID` o `killall nombre_proceso` |
| du | Mostrar el uso de espacio en disco | `du -h` |
| df | Mostrar el espacio disponible en disco | `df -h` |
| ifconfig | Mostrar información de red de interfaces de red | `ifconfig` |
| ping | Enviar paquetes de prueba a un host | `ping dirección_ip` |
| netstat | Mostrar estadísticas de red y conexiones | `netstat` |
| wget | Descargar archivos desde la web | `wget URL` |
| curl | Transferir datos con URL | `curl URL` |
| history | Mostrar historial de comandos | `history` |
| who | Mostrar quién está conectado al sistema | `who` |
| uname | Mostrar información del sistema | `uname -a` |
| man | Mostrar el manual de un comando | `man nombre_del_comando` |

### Administración de Usuarios y Grupos

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| chown | Cambiar el propietario y grupo de archivos | `chown nuevo_propietario:nuevo_grupo archivo` |
| chmod | Cambiar permisos de archivos y directorios | `chmod permisos archivo` o `chmod permisos directorio` |
| find | Buscar archivos y directorios | `find ruta -name "patron"` |
| grep | Buscar patrones en archivos y directorios | `grep "patron" archivo_o_directorio` |
| diff | Comparar contenido de archivos | `diff archivo1 archivo2` |
| tar | Comprimir y descomprimir archivos | `tar -cvf archivo.tar carpeta` (crear) o `tar -xvf archivo.tar` (extraer) |
| gzip / gunzip | Comprimir y descomprimir archivos (gzip) | `gzip archivo` (comprimir) o `gunzip archivo.gz` (descomprimir) |
| zip / unzip | Comprimir y descomprimir archivos (zip) | `zip archivo.zip archivo` (comprimir) o `unzip archivo.zip` (descomprimir) |

### Información del Sistema (Continuación)

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| uptime | Mostrar el tiempo de actividad del sistema | `uptime` |
| cron / crontab | Programar tareas para ejecutarse en momentos específicos | `crontab -e` (editar tareas programadas) |
| useradd / userdel / passwd | Administrar usuarios y contraseñas | `useradd nuevo_usuario` (crear) o `userdel usuario` (eliminar) o `passwd usuario` (cambiar contraseña) |
| groupadd / groupdel | Administrar grupos de usuarios | `groupadd nuevo_grupo` (crear) o `groupdel grupo` (eliminar) |
| sudo | Ejecutar comandos con privilegios de superusuario | `sudo comando` |
| su | Cambiar al usuario superusuario | `su` o `su usuario` |

---

### Administración del Sistema

#### Gestión de Procesos

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| `ps aux` | Mostrar todos los procesos en ejecución | `ps aux` |
| `top` | Mostrar información en tiempo real de procesos | `top` |
| `htop` | Interfaz más amigable para mostrar información de procesos | `htop` |
| `kill` | Finalizar procesos por su ID o nombre | `kill PID` o `killall nombre_proceso` |

#### Monitorización del Sistema

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| `free -h` | Mostrar información de memoria | `free -h` |
| `df -h` | Mostrar espacio en disco utilizado y disponible | `df -h` |
| `du -h` | Mostrar el uso de espacio en disco de directorios | `du -h` |
| `iotop` | Monitorizar la actividad de E/S en el sistema | `iotop` |
| `sar` | Recopilar y mostrar información del sistema | `sar` |


### Administración de Usuarios y Grupos

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| `useradd` | Agregar un nuevo usuario | `useradd nuevo_usuario` |
| `userdel` | Eliminar un usuario | `userdel usuario` |
| `passwd` | Cambiar la contraseña de un usuario | `passwd usuario` |
| `groupadd` | Agregar un nuevo grupo | `groupadd nuevo_grupo` |
| `groupdel` | Eliminar un grupo | `groupdel grupo` |
| `usermod` | Modificar propiedades de un usuario | `usermod -aG grupo usuario` (agregar a un grupo) |

### Servidores en la Nube

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| `ssh` | Conectar a un servidor remoto a través de SSH | `ssh usuario@direccion_ip` |
| `scp` | Copiar archivos de forma segura entre sistemas a través de SSH | `scp archivo usuario@direccion_ip:ruta_destino` |
| `rsync` | Sincronizar archivos y directorios entre sistemas de manera eficiente | `rsync -av origen destino` |

### Comandos para Docker y Contenedores

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| `docker-compose` | Definir y ejecutar aplicaciones multi-contenedor con Docker Compose | `docker-compose up` |
¡Entiendo! Aquí están los comandos del laboratorio en el formato específico que estás buscando:

### Ejecución de Comandos Manjaro Linux


### Comandos de la Práctica de Laboratorio

| Comando | Uso | Ejemplo de Uso |
| --- | --- | --- |
| `sudo pacman -Sy` | Actualizar paquetes disponibles en el sistema operativo | `sudo pacman -Sy` |
| `sudo pacman -S unrar zip unzip gzip bzip2` | Instalar paquetes para comprimir y descomprimir archivos | `sudo pacman -S unrar zip unzip gzip bzip2` |
| `sudo pacman -S yay` | Instalar el Repositorio AUR (Arch User Repository) | `sudo pacman -S yay` |
| `sudo yay -S --needed base-devel` | Instalar paquetes base para el desarrollo desde AUR | `sudo yay -S --needed base-devel` |
| `yay -S google-chrome` | Instalar Google Chrome a través de yay | `yay -S google-chrome` |
| `sudo pacman -S apache` | Instalar el servidor web Apache | `sudo pacman -S apache` |
| `sudo systemctl start httpd` | Iniciar el servicio de Apache | `sudo systemctl start httpd` |
| `uname -a` | Mostrar información del kernel del sistema operativo | `uname -a` |
| `git clone https://github.com/mortasoft/linux-scripts` | Clonar un repositorio de GitHub | `git clone https://github.com/mortasoft/linux-scripts` |
| `sudo useradd -m nombredeusuario -G wheel -p passworddelusuario` | Agregar un nuevo usuario con privilegios de sudo | `sudo useradd -m nombredeusuario -G wheel -p passworddelusuario` |
| `cp /etc/a* dirdos` | Copiar archivos de /etc cuyo nombre comienza con "a" a la carpeta dirdos | `cp /etc/a* dirdos` |
| `mv archivo0 dir004` | Mover el archivo archivo0 a la carpeta dir004 | `mv archivo0 dir004` |
| `history > historial.txt` | Guardar el historial de comandos en un archivo llamado historial.txt | `history > historial.txt` |
| `grep -rs "papirus" $HOME` | Buscar la palabra "papirus" en la carpeta home del usuario | `grep -rs "papirus" $HOME` |




