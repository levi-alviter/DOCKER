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

> **docker ps [OPTIONS]**  
> List containers  
>> -a Show all containers (default shows just running)  

> **docker start [OPTIONS] [CONTAINER]**  
> Start one or more stopped containers  
>> -a Attach STOUT/STDERR and forward signals
>> -i Attach container's STDIN (allows user to start typing commands)  
>> --name [STRING] Assign a name to the containerc  

> **docker rm [OPTIONS] [CONTAINER] [CONTAINER...]**  
> Remove one or more containers  

> **docker container prune [OPTIONS]**  
> Remove all stopped containers  
>> -f Do not prompt for confirmation  

> **docker rmi [OPTIONS] [IMAGE] [IMAGE...]**  
> Remove one or more images  

> **docker image inspect [OPTIONS] [IMAGE] [IMAGE...]**  
> Display detailed information on one or more images (in json by default)  

> **docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH**  
> **docker cp [OPTIONS] SRC_PATH CONTAINER:DEST-PATH**  
> Copy files/folders between a container and the local filesystem  

> **docker exec [OPTIONS] [CONTAINER] [COMMAND] **    
> Execute a command in a running container  
>> -i Keep STDIN open even if not attached  
>> -t Allocate a pseudo-TTY  

> **docker tag [SOURCE_IMAGE][:TAG] [TARGET_IMAGE][:TAG]**  
> Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE  

> **docker login**  
> Authenticate to a registry  
> Defaults to Docker Hub if no server is speficied  

> **docker logout**  
> Logout form a registry  

> **docker pull [OPTIONS] name[:TAG]**  
> Download an image from a registry  