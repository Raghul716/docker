#  Docker Swarm: 
The cluster management and orchestration features embedded in the docker Enhine are built using swarmkit.
A swarm consists of multiple docker hosts which run in swarm mode and act as a managers(to manage membership and delegation) and workers(which run swarm services).

# Host 
Docker host can be manager, a worker or perform both roles.

# Service: 
When you create a service, you define its optimal state(number of replicas, network and storage resources available to it, ports the services exposes to the outside world and more).

Docker Swarm: Docker Swarm maintains the service Desired state. For instance if a worker node becomes unavailable, Docker schedules that nodes tasks on other nodes.

Task: Task is a running container which is part of a swarm service and managed by a swarm manager.

# Nodes:
A node is an instance of the Docker engine participating in the swarm.
You can run one or more nodes on a single physical computer or cloud server but production swarm deployments typically include docker nodes distributed across multiple physical and cloud machines.
To Deploy your application to a swarm you submit service definition to a manager node. The manager node dispatches units of work called tasks to worker nodes.

# Manager nodes: 
also perform the orchestration and cluster management functions required to maintain the desired state of the swarm. Manager nodes elect a single leader to conduct orchestration tasks.

# Worker nodes: 
Receive and execute takss dispatched form manager nodes.

# Service: 
A service is the defination of the tasks to execute on the manager or worker nodes.
when you create a service you specify which container image to use and which commands to execute inside running containers.

# Task: 
A task carries a Docker container and the commands to run inside the container.
Once a task is assigned to a node it cannot move to another node. it can only run on the assigned node or fail.

# Load Balancing: 
Swarm manager uses ingress load balancing to expose the services you want to make available externally to the swarm.
External components such as cloud load balancers can access the service on the published port of any node in the cluster whether or not the node is currently running the task for the service.
All nodes in the swarm route ingress connections to a running task instance.

