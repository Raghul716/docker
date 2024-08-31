Issue: Container Persistent Data Problem
"Containers are immutable, meaning they cannot be modified directly. To upgrade a container, it must be redeployed. While files created within a container are stored on a writable layer, data persistence is not guaranteed. Once the container is removed, its data may be lost. Additionally, accessing data within a running container for use by another process can be challenging."

Docker has two options to solve this issue.
1. Volumes
2. Bind mounts

# Volumes: 
Are stored in a part of the host filesystem which is managed by Docker.

#docker run -d --name mysqldb -e MYSQL_ALLOW_EMPTY_PASSWORD=true --mount source=mysql-db1,destination=/var/lib/mysql mysql
#docker volume ls
DRIVER    VOLUME NAME
local     mysql-db1

#docker container stop mysqldb
#docker run -d --name mysqldb1 -e MYSQL_ALLOW_EMPTY_PASSWORD=true --mount source=mysql-db1,destination=/var/lib/mysql mysql

Here you see the volume mysql-db1 is attached to mysqldb and mysqldb1

# Bind Mounts:
Bind mount means a file or directory on the host machine is mounted into a container
Non-Docker processes on the docker host or a docker container can modify them at any time.
Bind Mount cannot be used in DockerFile.
Sharing the Configuration files from the host machine to containers.
Sharing source code or build artifacts between a development environment on the docker host and a container.

#######RUN Nginx with Bind Mount##########
docker container run -d --name nginx1 --mount type=bind,source=$(PWD),target=/app nginx
Example:
mkdir dockerbind
cd dockerbind
docker container run -d --name nginx1 --mount type=bind,source=$(pwd),target=/app nginx

