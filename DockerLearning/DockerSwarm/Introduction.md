#  Docker Swarm

Docker Swarm is a native container orchestration tool built into Docker that allows you to manage and scale a cluster of Docker containers across multiple hosts (nodes or virtual machines). It helps in automating the deployment, scaling, and management of containerized applications, making it easier to handle production workloads. Docker Swarm ensures that containers are efficiently managed, fault-tolerant, and scalable.
 
 >> Allows you to scale containers as per need
 >> Allows you to manage containers or recreate if they fail pr crash
 >> Allows you to upgrade the service within zero downtime.
 >> Allows you to manage containers in VMs and nodes

Docker Swarm is a clustering and scheduling tool for Docker containers.
➢ Swarm is Docker’s native support for orchestrating clusters of Docker
engines.
➢ Orchestration : Define nodes. Define services. Set how many nodes you
want to run and where, and you’re done.
➢ At a high level, Swarm takes multiple Docker Engines running on
different hosts and lets you use them together.

Docker Swarm : Docker Swarm have Two Type of Nodes
Master(Manager) and Worker.
➢ Every swarm starts out with one manager node designated as the leader.
➢ Swarm is highly available thanks to its implementation of the Raft
algorithm.
➢ Raft Algo : Raft is a consensus algorithm designed to achieve fault
tolerance in distributed systems.
The leader node is constantly checking in with its fellow manager nodes
and syncing their states.

➢ Nodes and Roles: In Raft, a cluster consists of multiple nodes, and each
node can have one of three roles: leader, follower, or candidate.
There is one leader at a time, and followers replicate the leader's actions.
➢ Leader Election: Algorithm starts with all nodes in the follower state.
○ If a follower doesn't receive communication from a leader for a
certain period (election timeout), it transitions to the candidate state
and requests votes from other nodes to become the leader.
○ If a candidate receives votes from the majority of the nodes, it
becomes the leader.

➢ Handling Failures:
○ If a leader fails, a new leader is elected through the election process.
○ Nodes can detect inconsistencies and missing entries in their logs
and update them by replicating the logs from the leader.

➢ Task Scheduling

➢ Load Balancing

➢ Rolling Updates

➢ Security














===
