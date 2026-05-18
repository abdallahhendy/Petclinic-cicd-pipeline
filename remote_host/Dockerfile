FROM ubuntu:24.04

RUN apt update && apt install -y openssh-server docker.io sudo

RUN useradd -m -s /bin/bash remote_user && echo "remote_user:1234" | chpasswd && adduser remote_user sudo

RUN mkdir /var/run/sshd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]