FROM debian

RUN apt-get -y update && \
	apt-get -y install wget && \
	apt-get install bzip2 && \
	mkdir ts3_server

ADD http://dl.4players.de/ts/releases/3.0.13.6/teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2 ts3_server_install.tar.bz2

RUN tar -xjvf ts3_server_install.tar.bz2 -C ts3_server --strip-components 1 && rm ts3_server_install.tar.bz2 

WORKDIR ts3_server

COPY ts3server.ini .

EXPOSE 9987
EXPOSE 30033 
EXPOSE 10022 
EXPOSE 10011 


ENTRYPOINT ["sh", "ts3server_minimal_runscript.sh", "inifile=ts3server.ini"]

# https://console.nodilex.com/fr/community/tutorials/13/installer-un-serveur-vocal-teamspeak-3-sur-linux-debian-ubuntu/
# https://tserverhq.com/clients/knowledgebase/132/How-do-I-use-the-ts3serverini-file.html
# https://docs.docker.com/samples/library/teamspeak/

# docker build -t ts3server .
# docker run -it --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ts3server