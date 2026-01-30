# Docker Repository

Repo with all the foundational knowledge of Docker and docker compose good practices.

### Foundation commands

> **docker run [OPTIONS] [CONTAINER]**  
> Create and run a new container  
> Options:  
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

> **docker rm [OPTIONS] [CONTAINER] [CONTAINER...]**  
> Remove one or more containers  

> **docker container prune [OPTIONS]**  
> Remove all stopped containers  
>> -f Do not prompt for confirmation  

> **docker rmi [OPTIONS] [IMAGE] [IMAGE...]**  
> Remove one or more images  

> **docker image inspect [OPTIONS] [IMAGE] [IMAGE...]**  
> Display detailed information on one or more images (in json by default)  



