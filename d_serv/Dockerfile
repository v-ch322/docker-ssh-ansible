FROM ubuntu:latest
RUN apt update && apt install -y nano
RUN apt -y install python3-apt
RUN apt install -y openssh-server
# july29.pub file should have chmod 644 as the public key
COPY july29.pub /root/.ssh/authorized_keys
RUN ["chmod", "644", "/root/.ssh/authorized_keys"]
COPY sshd_config /etc/ssh/sshd_config
EXPOSE 22
