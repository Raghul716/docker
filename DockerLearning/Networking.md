Docker Network: Connect Containers to other containers and connect containers to Host Machine. Docker containers and services can be connected with each other. Containers and Services don't need to be aware where they are deployed either it be in same host or multiple hosts Container and Services can communicate, whether your docker hosts run linux, Windows, or a mix of OS.

Each Container connect to virtual private network called "bridge". Bridge: This is default Network driver of Docker Containers which are deployed in default bridge network will be able to communicate with each other by using the IP addresses.

BEST PRACTICE to create Networks: network "sql_php_nwt" for mySQL and PHP containers network "mongo_nwt" for mongo and PHP containers

Bridge Networking: By default, containers are connected to a Docker bridge network, allowing them to communicate with each other on the same host

Overlay Networking: This model enables communication between containers across different hosts. Technologies like VXLAN or IPSec are often used to create virtual networks that span multiple hosts.

Container Network Interface: CNI is a specification that defines how container runtimes interact with networking plugins. It allows different containers runtime to be combined with various networking solutions.

To see the list of docker networks #docker network ls

To create a docker network #docker network create --driver network_type network_name

To get detailed info about a network #docker network inspect network_name/network_id

To delete a docker network #docker network rm network_name/network_id

To connect a running container to a network #docker network connect network_name/network_id container_name/container_id

To disconnect a running container to a network #docker network disconnect network_name/network_id container_name/container_id

To identify host port and container port

docker port container_name/container_id
To identify IP address of running container #docker inspect Container_name -f {{.NetworkSettings.IPAddress}}

To remove all unused network #docker network prune