# Assignment to Deploy Multi Node Service via Docker Swarm

Docker's Distributed Voting App

This solution uses Python, Node.js, .NET, with Redis for messaging and
Postgres for storage.

Archictecture

![image](https://github.com/user-attachments/assets/2320f7d4-5c12-4236-a7bc-ed5d46f9ce90)

This is combination of Several docker and compose/swarm file. 

App is designed by Docker community and available on Docker Hub for
Public use.

➢ This service need 1 Mount Volume, 2 Network and 5 Stack Services

➢ Two overlay network you can call frontend and backend is needed.


➢ Voting App:
○ Image : dockersamples/examplevotingapp_vote
○ Web front app
○ Publish this on port 5000, Listener Container Port 80
○ Publish 4 replicas
○ Publish on frontend overlay Network

➢ Redis:
○ Image : redis:alpine
○ Redis is used to Collect New Votes
○ Publish 4 replicas
○ Publish on frontend overlay Network 


➢ Worker:
○ Image : dockersamples/examplevotingapp_worker
○ A .NET worker which consumes votes and stores them
○ Publish 4 replicas
○ Publish on frontend & backend overlay Network


➢ DB Service:
○ Image : postgres:15-alpine
○ Mount Volume and mount to /var/lib/postgresql/data
○ Publish on backend network
○ Publish 1 replicas


➢ Result Service:
○ Image : dockersamples/examplevotingapp_result
○ Will display the Voting result
○ Publish on backend network
○ Publish on port 5001, Container port 80
○ Publish 1 replicas 


..


#  If you want to deploy all the service as docker stack please use the docker-stack.yml and command 
docker stack deploy -c docker-stack.yaml voting_app
