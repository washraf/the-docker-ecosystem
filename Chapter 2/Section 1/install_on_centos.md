# Install On CentOS

The used Version in the installation is CentOS 7 Core 64 Bit, this should be applicable to both native and virtualized environment.
For More information visit [docker docs](https://docs.docker.com/installation/centos/) 

##Installation with Script
Install latest updates to help you get the latest version of Docker

```$ sudo yum update```

Install Docker via Script

```$ curl -sSL https://get.docker.com/ | sh```

Run the Docker Engine

```$ sudo service docker start```

Test Docker Version

```$ docker version```

Incase of error use this command:

```yum install docker-selinux```

And To start docker

```sudo systemctl start docker```

Then Test Docker Version

##Installation from Source Code Repository (Without the Script)
Install latest updates to help you get the latest version of Docker
$ sudo yum update
Add the Repo to your package manager
$ cat >/etc/yum.repos.d/docker.repo <<-EOF
[dockerrepo]
name=Docker Repository
baseurl=https://yum.dockerproject.org/repo/main/centos/7
enabled=1
gpgcheck=1
gpgkey=https://yum.dockerproject.org/gpg
EOF
Install docker Package
$ sudo yum install docker-engine
Run the docker engine
$ sudo service docker start
Incase of error use this command:
yum install docker-selinux
And To start docker
sudo systemctl start docker
Test Docker Version
$ docker version
