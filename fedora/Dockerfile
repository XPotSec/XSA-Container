FROM fedora:latest

MAINTAINER KevinZonda <xsa-container@kevinzonda.com>

RUN dnf upgrade -y                && \
    dnf install -y openssh-server && \
    dnf clean all

RUN echo 'root:password' | chpasswd

RUN mkdir /var/run/sshd

RUN sed -ri 's/^#?PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
