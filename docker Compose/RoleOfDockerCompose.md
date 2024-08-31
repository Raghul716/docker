Consider you have an application, and there are multiple API's which is part of applications and for each API you are executing multiple containers
it is not possible to execute each containers.
To solve this issue you can use Docker Compose
Single Command for all Image building and container creation.

# Build Service<------------->Startup Service-------------> Tear Down service
# docker-compose build<------>docker-compose up<----------> docker-compose d

