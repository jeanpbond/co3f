
# Pull base image.
FROM       ubuntu:latest

MAINTAINER Kong TO <newlight77@gmail.com>

# Import MongoDB public GPG key AND create a MongoDB list file
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10 \
  echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-3.0.list && \
  apt-get update && \
  apt-get install -y \
  mongodb-org=3.0.6 \
  mongodb-org-server=3.0.6 \
  mongodb-org-shell=3.0.6 \
  mongodb-org-mongos=3.0.6 \ 
  mongodb-org-tools=3.0.6 \
  rm -rf /var/lib/apt/lists/*


# Define mountable directories.
VOLUME ["/data/db"]

# Define working directory.
WORKDIR /data

# Create the MongoDB data directory
RUN mkdir -p /data/db

# Expose ports.
#   - 27017: process
#   - 28017: http
EXPOSE 27017
EXPOSE 28017

# Set usr/bin/mongod as the dockerized entry-point application
ENTRYPOINT ["/usr/bin/mongod"]