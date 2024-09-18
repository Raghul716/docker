#  Manager Docker Secrets.

Secrets: Password, SSH Key, SSL certificate. any piece of sensitive data.

User can manage this sensitive data with docker swarm secrets.

Docker centrally manage this Data and send to only a container that need it.

Only Granted service and containers access the Secrets Data over the Network.

Another use case for using secrets is to provide a layer of abstraction between the container and a set of credentials.

How Swarm manage the secrets:

When a user adds a new secret to a swarm cluster this secret is sent to a manager using a TLS connection.

TLS is a cryptographic protocol that provides communications security over a network by providing communication encryption privacy and data integrity.

![image](https://github.com/user-attachments/assets/29b232c3-1115-49ca-92a3-377431a19315)

Containers work on mounted decrypted secrets which store at /run/secrets/<secret_name> in containers.

User can update a service to grant it access to additional secrets shared to it are unmounted from the in-memory filesystem for that container and flushed from the nodes memory.


