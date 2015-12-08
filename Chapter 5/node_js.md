# Node JS

In this demo we are going to create a container that hosts a NodeJS application.
This demo is based on [docker example](https://docs.docker.com/examples/nodejs_web_app/)

####Create NodeJS Application

Step 1: Create Package.Json file
{
  "name": "docker-ubuntu-hello",
  "private": true,
  "version": "0.0.1",
  "description": "Node.js Hello world app on ubuntu using docker",
  "author": "Yourname<Mail@Mail.com>",
  "dependencies": {
    "express": "3.2.4"
  }
}
####Step 2: Create Index.JS File
var express = require('express');

// Constants
var PORT = 8080;

// App
var app = express();
app.get('/', function (req, res) {
  res.send('Hello world\n');
});

app.listen(PORT);
console.log('Running on http://localhost:' + PORT);
####Step 3: Create A Docker File
FROM    ubuntu
#make ure apt is up to date
RUN apt-get update
# install nodejs and npm
RUN apt-get install -y nodejs npm  
# Get The Code 
COPY . /src
# Install app dependencies
RUN cd /src; npm install
EXPOSE  8080
CMD ["nodejs", "/src/index.js"]
####Step 4: Build The Image from Docker File
$ sudo docker build -t washraf/washraf .
Step 5: Run the Docker Image
$ sudo docker run -p 1234:8080 -d washraf/washraf
####Step 6: test the application
$curl -i localhost:1234
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 12
Date: Tue, 06 Oct 2015 23:57:48 GMT
Connection: keep-alive

Hello world
