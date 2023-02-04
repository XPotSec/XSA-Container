FROM ubuntu:latest

MAINTAINER KevinZonda <xsa-container@kevinzonda.com>

RUN apt-get update -y                 && \
    apt-get upgrade -y                && \
    apt-get install -y openssh-server && \
    rm -rf /var/lib/apt/lists/*

RUN echo 'root:password' | chpasswd

RUN mkdir /var/run/sshd

RUN sed -ri 's/^#?PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
