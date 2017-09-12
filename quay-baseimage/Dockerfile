FROM       ubuntu:16.04
MAINTAINER Bogdan Yaskov "https://github.com/AkelMaister"

RUN apt-get update && apt-get -y upgrade && apt-get install -y openssh-server
RUN mkdir /var/run/sshd && echo 'root:toor'|chpasswd

RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config && sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

EXPOSE 22

CMD    ["/usr/sbin/sshd", "-D"]
