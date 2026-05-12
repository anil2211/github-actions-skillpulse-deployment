# github-actions-skillpulse-deployment
This is the three applications deployment using the github actions.


create a three tier application

create a new folder .github/workflows in root
create a ci.yml file inside the workflows
workflow-job-steps-actions[WJSA]

ci.yml
name: CI workflow
jobs:
    build:  # job name
        runs-on: ubuntu-latest #github runner
        steps:


add secrets of docker hub in settings

then push this code on the github
and pipeline run successfully


launched ec2 instance 

sudo apt-get update
sudo apt-get install docker.io

sudo usermod -aG docker ubuntu
newgrp docker
docker ps

sudo apt-get install docker-compose-v2


docker-compose.yml

cd.yml
name: Cd workflow

on:
   workflow_run:
    

add secrets on github
host-ip address
username-ubuntu
password-pem file

