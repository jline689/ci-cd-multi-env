FROM debian:stable-slim

RUN apt-get update && apt-get install -y openssh-server git curl nginx nodejs npm && \
    mkdir -p /var/run/sshd && \
    useradd -ms /bin/bash deploy && echo "deploy:deploy" | chpasswd && \
    mkdir -p /home/deploy/.ssh && chmod 700 /home/deploy/.ssh

COPY sshd_config /etc/ssh/sshd_config

EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]
