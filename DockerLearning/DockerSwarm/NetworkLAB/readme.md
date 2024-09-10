1. Create an overlay Network.
# docker network create -d overlay <network_name>

2. Create Service on user Define Overlay Network
# docker service create --name <service_name> --network <network_name> -e POSTGRES_PASSWORD=mypassword <Image_name>

3. Create web service to acess the DB and same network
#  docker service create --name <service_name> --network <networ_name> -p 80:80 <image_name>



