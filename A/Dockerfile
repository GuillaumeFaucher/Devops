
#IMAGE TO PULL 
FROM ubuntu:latest

MAINTAINER TGB

#COMMANDE A EXECUTER
RUN mkdir -p /usr/src/app

#Repertoire
COPY ./API/app.js /usr/src/app/
COPY ./API/package-lock.json /usr/src/app/
COPY ./API/package.json /usr/src/app/
COPY docker-entrypoint.sh /

#Repertoire de travail 
WORKDIR /usr/src/app/

#COMMANDE A EXECUTER
RUN \ 
		apt-get update && \
		apt-get install -y curl && \
		curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -&& \
		apt-get install -y nodejs && \
		npm i

ENTRYPOINT ["/docker-entrypoint.sh"]