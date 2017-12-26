############################################################
# Dockerfile to build a MongoDB container image
# Based on Ubuntu
############################################################
################## BEGIN INSTALLATION ######################
# Set the base image to Ubuntu
FROM ubuntu

# File Author / Maintainer
MAINTAINER JiggaByte

# Update the repository sources list
RUN apt-get update

# Install MongoDB Following the Instructions at MongoDB Docs
# Ref: http://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/

# Add the package verification key
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10

# Add MongoDB to the repository sources list
RUN echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | tee /etc/apt/sources.list.d/mongodb.list

# Update the repository sources list once more
RUN apt-get update

# Install MongoDB package (.deb)
RUN apt-get install -y mongodb-10gen

# Create the default data directory
RUN mkdir -p /data/db

# Make directory/file writable
RUN chmod 755 /data/db

##################### INSTALLATION END #####################

# Expose the default ports
EXPOSE 27017
EXPOSE 28017

# Default port to execute the entrypoint (MongoDB)
CMD ["--port 27017"]

# Start (MongoDB)
CMD ["mongod"]

# Set default container command
ENTRYPOINT usr/bin/mongod