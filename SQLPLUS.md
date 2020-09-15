# SQLPlus

## Requirement

scp -i ~/.ssh/ords.pem ~/Documents/git/oracle/docker-db-apex-dev/sqlplus/* ubuntu@ec2-18-206-92-192.compute-1.amazonaws.com:/home/ubuntu/sqlplus/

## Package
apt-get install unzip

## Install
sudo mkdir /opt/oracle
sudo mv /home/ubuntu/sqlplus/* /opt/oracle
cd /opt/oracle

## Unzip
sudo unzip instantclient-basic-linux.x64-19.8.0.0.0dbru.zip
sudo unzip instantclient-tools-linux.x64-19.8.0.0.0dbru.zip
sudo unzip instantclient-sqlplus-linux.x64-19.8.0.0.0dbru.zip
sudo unzip instantclient-jdbc-linux.x64-19.8.0.0.0dbru.zip
sudo unzip instantclient-odbc-linux.x64-19.8.0.0.0dbru.zip
sudo unzip instantclient-sdk-linux.x64-19.8.0.0.0dbru.zip

sudo apt-get install libaio1

export LD_LIBRARY_PATH=/opt/oracle/instantclient_19_8:$LD_LIBRARY_PATH
export PATH=/opt/oracle/instantclient_19_8:$PATH
nano ~/.profile

## Add in ~/.profile

```
export PATH="$PATH:/opt/oracle/instantclient_19_8"
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/opt/oracle/instantclient_19_8"
```

source ~/.profile
