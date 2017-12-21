
# Ubuntu Dockerfile

# Team TGB

# Pull base image
FROM ubuntu

MAINTAINER tgb

# Installation
RUN \
      sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
      apt-get update && \
      apt-get -y upgrade && \
      apt-get -y install apt-utils && \
      apt-get install -y build-essential && \
      apt-get install -y software-properties-common && \
      apt-get install -y curl git  unzip wget nano && \
      rm -rf /var/lib/apt/lists/* && \

      apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10 && \
      echo "deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen" | tee -a /etc/apt/sources.list.d/10gen.list && \
      apt-get update && \
      apt-get -y install mongodb-10gen


# Variable d'environnement
  ENV HOME /root

# WorkDirectory
  WORKDIR /root

# Commande par défault
  CMD ["bash"]


#RUN echo "" >> /etc/mongodb.conf

  CMD ["/usr/bin/mongod", "--config", "/etc/mongodb.conf"]

# commande node js



# Les ports exposés
  EXPOSE 8080 27017

# les volumes
