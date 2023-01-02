FROM node

# set the working directly for COPY and RUN.
WORKDIR /app

# copy all local files into the image.
# COPY will execute relatively to the WORKDIR.
# COPY . /app if WORKDIR was not set , but you can still do it like this.
COPY . ./

# run a command in the image but first you need to set the WORKDIR to tell docker to run all the RUN commands in that directory.
# RUN will execute relatively to the WORKDIR.
# RUN is executed when the image is created, unlike CMD.
RUN npm install

# optional, will be replaced by '-p'.
# you need to add '-p <local port>:<docker container exposed port>''.
# a docker container is isolated, so we expose a port.
EXPOSE 80

# run the container based on the image.
# CMD is only execute when a container is started based on the image.
# the command is 'node server.js' but the CMD syntax needs an array contaning the commands.
CMD ["node" "server.js"]

# execute 'docker build .' in this path and you will build an image.
# execute 'docker run <id> -p <local port>:<docker container exposed port>' to run the built image.
# execute 'docker stop <id>' to stop the container, will not delete, so you can still run it using it's existing ID.