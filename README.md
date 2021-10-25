

# COMANDOS BASE PARA DOCKERS

# Para ver las imagenes locales
$ docker images
# ----------------------------------------------------------------------.

# Para descargar una imagen de DockerHub
$ docker pull "image-name"
# ----------------------------------------------------------------------.

# Para crear el contenedor de una imagen
$ docker run -d --name "alias-name" "image-name"
# docker run ejecuta 3 pasos, (valida existencia de contenerdor y si no lo descarga, hace docker create y docker start).
# Para habitar/exponer un puerto disponible automaticamente en el anfitrión 
$ docker run -d -P --name --name "alias-name" "image-name"
# Para habitar/exponer un puerto manualmente en el anfitrión
$ docker run -d -p 80:80/tcp --name "alias-name" "image-name"
$ docker run -d -p 192.168.0.120:80:80/tcp --name "alias-name" "image-name"
$ docker run -d -p 80:80/udp --name "alias-name" "image-name"
$ docker run -d -p 80:80/sctp --name "alias-name" "image-name"
# Siendo el puerto 80 y esa ip un ejemplo. doc https://docs.docker.com/engine/reference/commandline/run/#publish-or-expose-port--p---expose
# Ejemplo para una imagen con Node
$ docker run -u node -w /home/node/app -e NODE_ENV=production -p 3000:3000 --expose 3000 myapp-node node "app.js"
# ----------------------------------------------------------------------.

# Para ver los contenedores locales activos
$ docker ps
# Se puede filtrar por diferentes tag: status name etc.
# Para ver contenedores activos y no activos
$ docker ps -a
# ----------------------------------------------------------------------.

# Para crear un contenedor a partir de una imagen 
$ docker create --name "container-name" "image-name"
# ----------------------------------------------------------------------.

# CICLO DE VIDA
# Inicializando.
$ docker start "Container-name"
# Pausar
$ docker pause "container-name"
# Detener
$ docker stop "container-name"
# ----------------------------------------------------------------------.

# Eliminar
$ docker rm "container-name"
# ----------------------------------------------------------------------.


# Para acceder a terminal de un contenedor
$ docker exec -t --interactive "container-ID" /bin/sh o /bin/bash
$ docker run -t -i "container-name" /bin/sh o /bin/bash
# ----------------------------------------------------------------------.

# Para ver los Logs de un contenedor activo 
$ docker logs "container-name"

# Toda la documentación
https://docs.docker.com/engine/reference/commandline/ps/
# ----------------------------------------------------------------------.

