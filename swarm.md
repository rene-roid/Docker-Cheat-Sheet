swarm

swarm mode what is
- is a server cluster management tool built into Docker Engine

explain how swarm mode works


docker swarm init: initialize a swarm.
What happened?
- The current node becomes a manager node.
- A swarm is created.
- A root certificate is created.
- A join token is created.
- The current node is added to the swarm as a manager node.

docker node ls: list nodes in the swarm.

docker service: replaces docker run in the context of a swarm.

docker service create alpine ping 8.8.8.8: create a service that runs the alpine image and pings

docker service ls: list services in the swarm.

docker service ps intelligent_haslett: list tasks in the service.

docker service update <id> --replicas 3: update the number of replicas in the service.