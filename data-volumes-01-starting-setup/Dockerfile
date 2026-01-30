FROM node 

WORKDIR /app

COPY package.json /app/package.json

RUN npm install

COPY . /app

# ? by adding this env variable, it'll be available throughout the entire app
# ? new syntax. Use it! 
# ! this is only a default value, it can be assigned when running the container
# ! docker run --env PORT=8000 -p 3000:8000 feedback-node:env, 
# ! or docker run -e PORT=8000 -p 3000:8000 feedback-node:env
# ! you can assign as many as you want
# ! thanks to this you don't have to rebuild the image
# ENV PORT=80

# ? --------------------------------
# ? USING ARG
# ? ----------------------------------
# ? ARGS -> CANNOT BE USED IN THE CODE AS ENV
# ? BUT ONLY IN THE DOCKER FILE. 
# ! EXCEPT IN THE CMD WHICH IS A RUNTIME COMMAND
# ! THIS ARG IS ASSIGNED WHEN BUILDING THE IMAGE
# ! docker build --build-arg DEFAULT_PORT=8000
ARG DEFAULT_PORT=80

# ? to use docker arg you must follow the structure ${arg}
ENV PORT=${DEFAULT_PORT}

# ! OR you can create and env file and use the command
# ! docker run --env-file (location of the file)
# ! docker run --env-file ./.env

# ! for security reasons prefer --env-file approach as it is used only when running not while
# ! developing, otherwise the hardcoded variables can be seen in the docker history

# ? to use an env variable you have to put a dollar sign in front of it
# EXPOSE $PORT

# ? creating our first volume
# ! this route points to the route in the container's files system
# ! two kinds of volumes anonymous and named volumes
# ! anonymous -> docker defines their location automatically, they exist as longer as containers exist
# ! the local path is defined somewhere by docker
# VOLUME [ "/app/feedback" ]

# ! name volumes -> persists even though the container is gone
# ? name volumes are created when running a container
# ! docker run (dir-name locally):(dir-name container) image-name/id -> runs a container with a name volumen
# ! docker run feedback:/app/feedback volumepractice:v8

# ! neither anonymous or named volumes location's are know 

# ? bind mounts location can be known -> we the devs set the path
# * Volume is good for persisting data in the container and isolated.
# * Bind mounts is good for persisting data and editions coming from outside

# * for both bind mounts and volumes the changes on container are reflected on local machine and vice versa

# ! for bind mounts make sure docker has permission to access the folder
# ! to add a new dir: docker desktop -> settings -> resources -> file sharing -> add your dir or parent of dir

# ! when using bind mounts the changes from outside are made in the container, not backwards
# VOLUME [ "/app/node_modules" ]

# ! when working with bind mounts add previous line to preserve node_modules, as the non existing 
# ! node_modules overwrite the node_modules of the container, the previous line creates a volume
# ! and the rule for docker to select which date preserve is by the most specific path (yeah bind mounts 
# ! only points to /app, but /app/node_modules is more specific) 
# ! this can be achieved by writing the anonymous volume here on during the running of the container

# ? docker run -d -p 80:80 -v "%cd%":/app -v feedback:/app/feedback -v /app/node_modules --name volumeApp11 volumepractice:v8
# ? runs the container creating a named volume to feedback, creating a bind mount to reflect the changes on the
# ? code into the container, and preserving the node_modules from the host changes, and some other stuff

# ! by default bind mount are read-write
# ! v (internal-path):ro -> to make volumes read only

CMD [ "npm", "start"]