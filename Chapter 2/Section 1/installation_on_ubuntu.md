# Installation On Ubuntu

1 - Add the new gpg key.


    $ sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
2 - add the repo location

    $ sudo vi /etc/apt/sources.list.d/docker.list
    
3 - based on you version add ```deb https://apt.dockerproject.org/repo ubuntu-trusty main```

4 - Update Package manager ```$ apt-get update```

5 - 