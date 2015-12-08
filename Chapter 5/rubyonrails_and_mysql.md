# RubyonRails and mysql

##Create MySQL server
Mysql is by far the most used database in the open source community so a docker image have been created with mysql installed on it.
####Step 1: Create Docker File
Create a folder name mysqlImage and create Dockerfile that contains the instructions needed for the image.

```#mkdir mysqlImage```

```#cd mysqlImage```

```#vi Dockerfile```

In the docker file write the needed configurations:

{%ace edit=false%}
# Version: 0.0.1
FROM mysql
#use mysql image to be our base image
MAINTAINER Name name@name.com
VOLUME /SQLDBFILES:/var/lib/mysql
#set the Database super user password
ENV MYSQL_ROOT_PASSWORD w@lid
#make sure that mysql Server is running
RUN service mysql start
# The Image default expose
# EXPOSE 3306
{%endace%}
####Step 2: Build docker Image
```# docker build –t washraf/mysql .```
####Step 3: run the container
```# docker run --name wsql -d washraf/mysql```
####Step 4: find the assigned IP
```# docker inspect wsql```

##Ruby on Rails
####Step 1: create the project and configure it to use MySQL

####Step 2: configure the database source in the code
{%ace edit=false%}
username: root #the user you uses
password: w@lid #the password you save
host: 172.17.0.61 #the assigned ip
{%endace%}
####Step 3: Create a deployment and run script SCRIPT.sh
{%ace%}
/bin/bash
# My first script
cd /root/trial
bundle install
rake db:create
rake db:migrate
rails server -b 0.0.0.0
{%endace%}
####Step 4: Create Dockerfile
From rails
COPY /trial/ /root/trial/
COPY /SCRIPT.sh /root/
#ENTRYPOINT /root/SCIRPT.sh
EXPOSE 3000
####Step 5: Build DockerFile
docker build --no-cache -t washraf/rails .
Step: start the container
docker run -d -p 3000:3000  washraf/rails /root/SCRIPT.sh
