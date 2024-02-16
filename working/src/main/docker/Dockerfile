FROM alpine:latest

WORKDIR /app

COPY . /app

RUN apk update
EXPOSE 22
RUN apk add openssl
RUN apk add python3
RUN apk add ansible
RUN apk add --no-cache openssh
RUN apk add openssh-server
RUN apk add openssh-client
RUN apk add vim
RUN apk add sshpass
RUN apk add openrc
RUN rc-update add sshd
RUN rc-status
RUN touch /run/openrc/softlevel
RUN rc-service sshd restart
RUN ssh-keygen -A
RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
RUN echo "Port 22" >> /etc/ssh/sshd_config
RUN echo "PermitEmptyPasswords yes" >> /etc/ssh/sshd_config
RUN echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config
RUN rc-service sshd restart

# RUN echo “root:196711aa” | passwd
# Need to restart rc-service sshd

# Next, need to create a script that runs the above manual commands and
# that sets up the local network, and adds host fingerprints, restarts sshd
