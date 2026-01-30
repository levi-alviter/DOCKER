# ? FROM -> write your image from another one
# ? from either your system or docker hub
# ? in this case from node available on docker hub
FROM node

# ? COPY -> to copy local files into container
# ? COPY (HOST FILE SYSTEM) (CONTAINER FILE SYSTEM)
# ? THE FIRST DOT MEANS TAKE ALL THE FOLDERS, SUBFOLDERS AND FILES IN THEM 
# ? THE SECOND DOT MEANS COPY THE TAKEN FILES INTO THE CONTAINER'S FILE SYSTEM ROOT
# COPY . .

# ? this indicates docker all the subsequents commands (npm) will have to be run 
# ? in /app
WORKDIR /app

# ? in this case the files will be coped into /app folder.
# ? app folder will be created automatically
# ? COPY . ./app -> without workdir

# ? by doing this the if package.json /app has no changes the cache is used
# ? and npm install can use the cache as well
COPY package.json /app

# ! by default all the commands will be run on the root directory
RUN npm install

# ! as we have WORKDIR we can just simply say 
# COPY . ./
# ? COPY everything into ./ which is my WORKDIR in this case /app
# ? as the code is mutable, the cache use is interrupted here
# ? which is ok, as the heavy part is RUN npm install
COPY . /app

# ? letting the container expose the port 80, when it's started
EXPOSE 80

# ! CMD has to be the last instruction
# ? CMD has another structure
CMD ["node", "server.js"]

# ! RUN executed when building the image
# ? CMD run when initing the image
# ! if you use node server.js in run you'll set up a node server every time 
# ! you build the image

# ? docker build (route to the Dockerfile) -> to build the container from an imaage
# ? docker run (image id) -> run the container 
# ! docker run -p (local port):(container port) (image id) -> to connect my local 3000 port with the exposed 80 of the container
# ! docker run -p 3000:80 (image id) 

# ! docker ps -> to see the docker processes
# ? docker stop (container name) -> stop the container


# ! IMPORTANT: Docker caches every line (layer)
# ! if there  is no change in the result of the line docker use the cach of
# ! each line
# ! if docker finds a change, the caches is nulled and the lines re-executed