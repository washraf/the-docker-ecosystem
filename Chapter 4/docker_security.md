# Docker Security

##Docker Sockets and Network Ports
Docker registered its own TCP port with IANA and it’s now generally configured to use TCP port 2375 when running un-encrypted, or 2376 when handling encrypted traffic. In Docker 1.3 and later, the default is to use the encrypted port on 2376, but this is easily configurable. The UNIX socket is located in different paths on different operating systems, so you should check where yours is located. If you have strong preferences, you can usually specify this at install time. If you don’t, then the defaults will probably work for you.
####Configuring sockets and security

##Docker non root main user
