FROM debian:latest-slim

MAINTAINER KevinZonda <xsa-container@kevinzonda.com>

RUN apt-get update -y                 && \
    apt-get upgrade -y                && \
    apt-get install -y openssh-server && \
    apt-get install -y locales        && \
    rm -rf /var/lib/apt/lists/*       && \
    localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8

ENV LANG en_US.utf8

RUN echo 'root:password' | chpasswd

RUN mkdir /var/run/sshd

RUN sed 's/PermitRootLogin without-password/PermitRootLogin yes/' -i /etc/ssh/sshd_config

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
