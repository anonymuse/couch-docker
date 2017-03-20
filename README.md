# Couchbase on Swarm

This repository shows you how to build a simple Couchbase cluster with a master and worker node. We'll use the built in Swarm capabilities of Docker for Mac, so you can get started quickly.

## Prerequisites

Docker for Mac

Docker engine 1.13+

## Getting Started

Make sure the latest Docker for Mac is installed. You can get it from here.

Now, we can make sure that you have a clean swarm to work with. This will remove any working services that you have currently running, so please use care when cleaning up.

First, let's leave the swarm on our Mac.

```
$ docker swarm leave --force
Node left the swarm.
```

```
$ docker swarm init
Swarm initialized: current node (lba3zk5zl26ov244tbh7jzq42) is now a manager.

To add a worker to this swarm, run the following command:

    docker swarm join \
    --token SWMTKN-1-5uxr8sgw334copzg87nc5eemjqk7cb7guru916nflbj25omzq5-bunwv4jby0gu11y7yxxz1jegh \
    192.168.65.2:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.$
```

Great! Now we can launch our service and check on the health of the cluster

```
$ docker deploy -c docker-compose.yml couchbase
Creating network couchbase_couchbase
Creating service couchbase_couchbase-worker
Creating service couchbase_couchbase-master
$
```
