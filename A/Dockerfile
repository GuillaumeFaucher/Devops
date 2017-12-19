
# Ubuntu Dockerfile

# Team TGB

# Pull base image.
FROM ubuntu:16.04

# Installation
RUN \
      sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
      apt-get update && \
      apt-get -y upgrade && \
      apt-get install -y build-essential && \
      apt-get install -y software-properties-common && \
      apt-get install -y byobu curl git htop man unzip vim wget nano && \
      rm -rf /var/lib/apt/lists/* && \

      apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10 && \
      echo "deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen" | tee -a /etc/apt/sources.list.d/10gen.list && \
      apt-get update && \
      apt-get -y install apt-utils && \
      apt-get -y install mongodb-10gen && \

      apt-get install -y software-properties-common python  && \
      add-apt-repository ppa:chris-lea/node.js  && \
      echo "deb http://us.archive.ubuntu.com/ubuntu/ precise universe" >> /etc/apt/sources.list  && \
      apt-get update  && \
      apt-get install -y nodejs=8*   && \
      mkdir /var/www



# Ajout de ficher
  ADD root/.bashrc /root/.bashrc
  ADD root/.gitconfig /root/.gitconfig
  ADD root/.scripts /root/.scripts
  ADD app.js /var/www/app.js

# Variable d'environnement
  ENV HOME /root

# WorkDirectory
  WORKDIR /root

# Commande par défault
  CMD ["bash"]


#RUN echo "" >> /etc/mongodb.conf

  CMD ["/usr/bin/mongod", "--config", "/etc/mongodb.conf"]

# commande node js
  CMD ["/usr/bin/node", "/var/www/app.js"]


# Les ports exposés
  EXPOSE 8080
  EXPOSE 27017
