# Scaling-replicas-Docker

Steps to increase the number of replicas of a task for any given service-

```

1. List the Docker services
$ sudo docker service ls

2. Scale up the redis service to five tasks
$ sudo docker service scale redis=5

3. Scale the registry service to four tasks using update flag
$ sudo docker service update --replicas=4 registry

4. Use the scale flag to scale both redis and registry services at the same time
$ sudo docker service scale redis=4 registry=3

5. Check the actual number of replicas created
$ sudo docker service ls

6. Create a global service and scale it up to ten tasks
$ sudo docker service create --mode global --name nginx nginx:latest
$ sudo docker service scale nginx=10

Note: Notice that the scaling cannot be used with global services. It can only be done with replicated service.

```

