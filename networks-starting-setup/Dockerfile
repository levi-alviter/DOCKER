FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD ["node", "app.js"]

# ! Three kinds of communication 

# ? 1) Container to wwww
# ? containers can send requests to the www, by default
# ? not necessary to tweak the code or make an adjustment to make it work

# ? 2) Container to local machine
# ? code need to be tweaked turning localhost into host.docker.internal every time is encountered

# ! previously docker run mongo command was run -> from docker hub
# ? 3) Container to container
# ? if you need the IP address look for the ip address of the container's service
# ? using docker container inspect container-name 
# ? look for the "NetworkSettings" and find the port and IPAddress


# ? OOOOOOOOOOOOORRRRRRR 
# ? you can user docker networks

# ? Steps 
# ? 1) you have to create it first on your own
# ?     - docker network create network-name -> docker network create favorites-net
# ?     - docker run --network network-name 

# ? 2) then you have to use it
# ? docker run --network network-name image-name
# ? docker run --network favorites-net mongo
# ? this adds the container to the docker container
# ? reach out to the container by calling mongodb:{container-name}:port/...
# ? reach out to the container by calling mongodb:mongodb:27017/swfavorites
# ? the transformation of the IP will be done automatically by docker

# ! containers are not able to talk each other unless they're in the same network, and pointed by container name
# ! or you point to their ip address -> less recommended

# ! -p is only used when incoming requests are sent from local machine to container
# ! not necessary for containers in the same docker network