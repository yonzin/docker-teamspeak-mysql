# docker-teamspeak-mysql
teamspeak using mysql database

add missing mysql libraries libmysqlclient.so.15 and libts3db_mysql.so

## Installation
   ```bash
    git clone https://github.com/yonzin/docker-teamspeak-mysql
    cd docker-teamspeak-mysqli
    ## edit files/config/ts3server.ini and files/config/ts3db_mysql.ini as needed
    docker build -t yonzin/teamspeak .
```

## Usage
default ports are 9987, 10011, 30033
```bash
    docker run -d -name teamspeak \
        -p 9987:9987/udp \
        -p 10011:10011 \
        -p 30033:30033  \
        -v /opt/teamspeak/logs:/opt/teamspeak/logs \
        -v /opt/teamspeak/ts3server.ini:/opt/teamspeak/ts3server.ini \
        -v /opt/teamspeak/ts3db_mysql.ini:/opt/teamspeak/ts3db_mysql.ini \
        yonzin/teamspeak
```
## Volumes
list of available volumes:
* /opt/teamspeak/ts3server.ini : teamspeak config file
* /opt/teamspeak/ts3db_mysql.ini : teaspeak database config file
* /opt/teamspeak/logs : teamspeak logs

## Mysql ini file
File from /opt/teamspeak/ts3db_mysql.ini
```
[config]
host=mysql_host
port=mysql_port
username=mysql_username
password=mysql_password
database=mysql_database
socket=
```
