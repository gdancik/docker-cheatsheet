# docker-cheatsheet

Some example docker commands

### Use *docker run* to launch a container

Use the `-it` flag to launch the container in interactive mode. The code belows creates a container running 'centos', a linux distribution. 

```
docker run -it centos
```

You are now inside a terminal in the centos container. Simply type `exit` to exit the container.

Let's launch the container again, but use the `-d` flag to run the container in the background:

```
docker run -itd centos
```

Let's launch another container, but use the `--name` argument to give the container a name.

```
docker run -itd --name my_container centos
```

### Use *docker ps* to view jobs (containers)

```
docker ps
```

Note that each container has a CONTAINER ID and a NAME.

Use the `-a` tag to list *all* containers, including stopped ones.

```
docker ps -a
```

### Use *docker exec* to execute a command in a running container

The format is `docker exec [arguments] conainer_id command`.

Note that for the *container id*, you just need to specify enough characters to uniquely identify the container.
For example, if there are two containers, 3a4534 and 3c9999, then you can use *3c* to identify the second container.
You can also reference the container by *name*, which must match exactly.

### Run *ls* inside the container to list files in the root directory

```
docker exec 3c ls
```
### Run *bash* inside the container to open an interactive terminal inside the container
```
docker exec 3c -it bash
```

Type `exit` to exit the container.

### Use *docker start* and *docker stop* to start and stop containers

Stop the above container

```
docker stop 3c
```

You can verify that the container is stopped using `docker ps` and `docker ps -a`.

### Use *docker system prune* to remove stopped containers

```
docker system prune
```


