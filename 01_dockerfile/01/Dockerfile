FROM debian

RUN apt-get -y update && \
	apt-get -y install wget && \
	apt-get install bzip2 && \
	mkdir ts3_server

ADD http://dl.4players.de/ts/releases/3.4.0/teamspeak3-server_linux_amd64-3.4.0.tar.bz2 ts3_server_install.tar.bz2

RUN tar -xjvf ts3_server_install.tar.bz2 -C ts3_server --strip-components 1 && rm ts3_server_install.tar.bz2 

WORKDIR ts3_server

# mv teamspeak3-server_linux_x86 ts3_server &&