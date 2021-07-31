FROM ubuntu:latest
WORKDIR /work
RUN apt update && apt install -y nano
RUN apt install -y openssh-client
RUN apt -y update
RUN apt -y install software-properties-common
RUN apt-add-repository ppa:ansible/ansible
RUN apt -y update && apt -y install ansible
RUN apt install -y python3-pip
RUN pip3 install boto boto3
ENV ANSIBLE_HOST_KEY_CHECKING=False
# july29 file should have chmod 400 as the public key
COPY july29 /root/.ssh/july29
RUN ["chmod", "400", "/root/.ssh/july29"]
EXPOSE 22
