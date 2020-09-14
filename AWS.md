# AWS

## Connect AWS
```
ssh -i ~/.ssh/ords.pem ubuntu@ec2-18-206-92-192.compute-1.amazonaws.com
```

## Initial
```
sudo apt-get remove docker docker-engine docker-ce docker.io
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-key fingerprint 0EBFCD88

sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
```

## Dockerfile
git clone https://github.com/PhyrexTsai/docker-db-apex-dev.git

## SCP
scp -i ~/.ssh/ords.pem ~/Documents/git/oracle/docker-db-apex-dev/temp/* ubuntu@ec2-18-206-92-192.compute-1.amazonaws.com:/home/ubuntu/docker-db-apex-dev/files/

## Build Docker Image
sudo docker build -t db-apex-dev-image .

## Run Docker Image
sudo docker run -d --name db-apex-dev-container -p 2222:22 -p 8080:8080 -p 1521:1521 -v /dev/shm --tmpfs /dev/shm:rw,nosuid,nodev,exec,size=2g db-apex-dev-image

## Install SQLPlus
[SQLPLUS.md](SQLPLUS.md)

## Setup ORDS
[ORDS.md](ORDS.md)
