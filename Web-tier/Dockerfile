# // Dockerfile sets up a Docker image for running a Node.js application. It creates a working directory, copies the necessary files, 
#    installs dependencies, and specifies the port and command to run the application.

# Select node version and set working directory
FROM node:17-alpine 
# This line specifies the base image for the Docker image. In this case, it uses the official Node.js 17 image with the Alpine Linux distribution as the base.
# This image provides a lightweight and minimal environment to run Node.js applications
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
# These lines create a directory named /usr/src/app inside the Docker container and set it as the working directory. 
#  This is where the application code will be placed and where subsequent commands will be executed.
COPY package.json /usr/src/app
# Install app dependencies: This line copies the package.json file from the local directory into the Docker container's /usr/src/app directory.
# The package.json file typically contains the dependencies and configuration for the Node.js application.
RUN npm install
# This command runs npm install inside the Docker container, which installs the dependencies specified in the package.json file. 
# It ensures that the required packages are installed within the container.
COPY . /usr/src/app
# Bundle app source: This line copies the entire content of the local directory (where the Dockerfile resides) into the Docker container's /usr/src/app directory. 
# It includes all the application source code and any other files necessary for the application to run.
EXPOSE 3000
# Expose publc port and run npm command; This line specifies that the container will listen on port 3000. 
# It informs Docker that the application inside the container will be accessible on this port.
CMD ["npm", "start"]
# This is the command that will be executed when a container is started based on this image. 
# It specifies that the npm start command should be run, which typically starts the Node.js application defined in the package.json file.
