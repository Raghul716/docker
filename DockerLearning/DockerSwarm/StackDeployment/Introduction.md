# Stack is a group of interrelated services that share dependencies, and can be orchestrated and scaled together.
A single stack is capable of defining and co-ordinating the functionality of an entire application.
Complex Application may have multiple stacks as well.
Docker stack uses Composes YAML format and complements the swarm specific properties for service deployments.
File name could be like docker-stack.yml



docker build --tag webapp .
docker image ls
docker tag webapp:latest Raghul716/webapp:1.0
docker push Raghul716/webapp:1.0
docker stack deploy -c docker-compose.yml webapp


Before deploying stack push the image to docker central repository
