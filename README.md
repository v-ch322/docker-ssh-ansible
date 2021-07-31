This repo was created for work with Ansible in inner net (Docker-compose net).

It was checked under Ubuntu 20.04 LTS.

The operations made by docker-compose are:

Creation of SSH-client (cli) and SSH-server (serv) containers with keys (of necessary chmod) and providing connection.

Installation of Ansible in SSH-client container.

Docker (I used 20.10.7) and docker-compose (I used 1.29.2) should be preliminary installed.

To run this application do:

1. Clone the repo by the command:

git clone https://github.com/v-ch322/docker-ssh-ansible.git


2. Then:

cd docker-ssh-ansible/

docker-compose up -d

3. After making the net and the containers it should to enter SSH_client container:

docker exec -it cli /bin/bash

4. Enter the ansible/nginx directory:

cd /ansible/nginx

5. Run playbook by the command:

ansible-playbook -i myhost make_Nginx.yml

6.After running the playbook you can see a result (static web-page) on the port

127.0.0.1:8000.

P.S. You can add your playbook placing the necessary files in 'ansible' directory of the cloned repo,
they will be placed in the container after the running of 'docker-compose up -d'.
Then you can run your playbook, the routine was fulfilled in 'serv' container.
