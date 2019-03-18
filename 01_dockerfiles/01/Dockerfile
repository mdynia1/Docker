FROM debian

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

EXPOSE 9987/udp 
EXPOSE 10011 
EXPOSE 30033

RUN apt-get update -y && \
	apt-get upgrade -y && \
	apt-get install bzip2 wget -y && \
	wget http://dl.4players.de/ts/releases/3.0.13.4/teamspeak3-server_linux_amd64-3.0.13.4.tar.bz2 && \
	bunzip2 *.bz2 && \
	tar -xvf *.tar

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

#to run it: docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 name