# Docker Repository

Repo with all the foundational knowledge of Docker and docker compose good practices.

### Foundation commands

> **docker run [OPTIONS] [IMAGE] [COMMAND]**  
> Create and run a new container  
> If image name is not found locally it's pulled and run from registry    
>> -i Keep STDIN open even if not attached  
>> -t Allocate a pseudo-TTY  
>> -p Publish a container's port(s) to the host -> -p HOST_PORT:CONTAINER_PORT  
>> -d Run container in background and print container ID  
>> --rm Automatically remove the container and its associated anonymous volumes when it exits  
>> --name string Assign a name to the container  
>> -v Mount a volume  
>> [EXISTING_NAMED_VOLUME] -> Reuse a volume
>>> [CONTAINER_TARGET_PATH] -> anonymous volume  
>>> [VOLUME_NAME]:[CONTAINER_TARGET_PATH] -> named volume  
>>> [HOST_ABSOLUTE_SOURCE_PATH]:[CONTAINER_TARGET_PATH] -> bind mount    
>>> %cd% -> Windows command to extract current path    
>>> $(pwd) -> Linux command to extract current path  
>>> [CONTAINER_TARGET_PATH]:ro -> turn volume only readonly

> **docker ps [OPTIONS]**  
> List containers  
>> -a Show all containers (default shows just running)  

> **docker start [OPTIONS] [CONTAINER]**  
> Start one or more stopped containers  
>> -a Attach STOUT/STDERR and forward signals
>> -i Attach container's STDIN (allows user to start typing commands)  

> **docker rm [OPTIONS] [CONTAINER] [CONTAINER...]**  
> Remove one or more containers  

> **docker container prune [OPTIONS]**  
> Remove all stopped containers  
>> -f Do not prompt for confirmation  

> **docker images [options]**  
> List images  
>> -a Show all images (default hides intermediate images)  

> **docker rmi [OPTIONS] [IMAGE] [IMAGE...]**  
> Remove one or more images  

> **docker image prune [OPTIONS]**  
> Remove unused images  
> -a Remove all unused images, not just dangling ones  

> **docker image inspect [OPTIONS] [IMAGE] [IMAGE...]**  
> Display detailed information on one or more images (in json by default)  

> **docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH**  
> **docker cp [OPTIONS] SRC_PATH CONTAINER:DEST-PATH**  
> Copy files/folders between a container and the local filesystem  

> **docker exec [OPTIONS] [CONTAINER] [COMMAND]**    
> Execute a command in a running container  
>> -i Keep STDIN open even if not attached  
>> -t Allocate a pseudo-TTY  
>> bash | sh different terminals you can connect to

> **docker tag [SOURCE_IMAGE][:TAG] [TARGET_IMAGE][:TAG]**  
> Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE  

> **docker login**  
> Authenticate to a registry  
> Defaults to Docker Hub if no server is speficied  

> **docker logout**  
> Logout form a registry  

> **docker pull [OPTIONS] name[:TAG]**  
> Download an image from a registry  

> **docker volume ls [OPTIONS]**  
> List volumes  

> **docker volume rm [OPTIONS] [VOLUME] [VOLUME...]**  
> Remove one or more volumes. You cannot remove a volume that is in use by a container  

> **docker volume prune [OPTIONS]**  
> Remove unused local volumes  
>> -f Do not prompt for confirmation  

> **docker logs [OPTIONS] [CONTAINER]**
> Fetch the logs of a container  

> **docker inspect [VOLUME]**  
> Get additional information of a volume  

> **docker volume rm [OPTIONS] [VOLUME] [VOLUME...]**  
> Remove one or more volumes. You cannot a volume that is in use by a container  
>> -f Force the removal of one or more volumes  