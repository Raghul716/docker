Issue: Container Persistent Data Problem
"Containers are immutable, meaning they cannot be modified directly. To upgrade a container, it must be redeployed. While files created within a container are stored on a writable layer, data persistence is not guaranteed. Once the container is removed, its data may be lost. Additionally, accessing data within a running container for use by another process can be challenging."

Docker has two options to solve this issue.
1. Volumes
2. Bind mounts

Volumes: Are stored in a part of the host filesystem which is managed by Docker.

