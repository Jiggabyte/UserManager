############################################################
# Dockerfile to build an Application/App dependencies
# container image
# Based on Ubuntu
############################################################
################## BEGIN INSTALLATION ######################
# Set the base image to Ubuntu
FROM ubuntu

# File Author / Maintainer
MAINTAINER JiggaByte

# Update the repository sources list
RUN apt-get update

# Fixing unmet dependencies
RUN apt-get -f install

# Install nodejs
RUN apt-get install -y nodejs-legacy

# Install npm
RUN apt-get install -y npm

# Install git
RUN apt-get install -y git

# clone git repository
RUN git clone https://github.com/Jiggabyte/UserManager.git

# Move into application directory
RUN cd UserManager

# Update app packages
RUN npm install

##################### INSTALLATION END #####################

# Expose port
EXPOSE 3000

# Set working directory
WORKDIR /UserManager

# Start app server
CMD ["npm","start"]