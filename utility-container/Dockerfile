# ? 14-alpine -> slimmer version
FROM node:14-alpine

WORKDIR /app

# ? CMD [ "" ] -> can be overwritten when running the container

# ? ENTRYPOINT [ "" ] -> every extra line or command is appended
# ? this way all the lines written will be npm commands
ENTRYPOINT [ "npm" ]

# ? command to run the container -> docker run -it -v %cd%:/app  --name node-util-container node-util npm init
# ? command to run the container -> docker run -it -v %cd%:/app  --name node-util-container node-util npm install express
