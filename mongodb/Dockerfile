FROM ubuntu:18.04
RUN apt update; apt install -y gnupg2; apt-get install -y gnupg 
RUN apt install -y software-properties-common;apt-get install -y wget
RUN wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | apt-key add - && \
	echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/6.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-6.0.list && \
	apt-get update && apt-get install -y mongodb-org
RUN mkdir -p /data/db
RUN chown -R mongodb:mongodb /data/db

ADD mongodb.conf /etc/mongodb.conf

VOLUME ["/data/db"]
EXPOSE 27017
ENTRYPOINT ["/usr/bin/mongod", "--config", "/etc/mongodb.conf"]
 
