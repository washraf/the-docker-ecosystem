# Wordpress and mysql

This demo will allow you to create a two tier application using ruby on rails and mysql.

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
```# docker run --name wpsql -d washraf/mysql```
##Create My WordPress container
####Step 1: run the wordpress image
```# docker run -p 80:80 --link wpsql:mysql -d  wordpress```
####Step2: open the browser

