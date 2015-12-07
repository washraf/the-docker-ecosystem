# Advanced Network Configuration

Docker creates a virtual interface and switch named docker0 to connect different container and enable each container to have its own network configuration.

Docker configures this switch to private network ip **172.17.42.1/16** allowing **65536** ip and The **MAC address** is generated using the IP address allocated to the container to avoid ARP collisions, using a range from **02:42:ac:11:00:00** to **02:42:ac:11:ff:ff**.

For more check this [article about docker networking]( https://docs.docker.com/articles/networking/)
###Docker0
Docker0 is the virtual interface created by the docker daemon in the installation time.

```$ ifconfig docker0```

The **second** line of the output: 

    inet 172.17.42.1  netmask 255.255.0.0  broadcast 0.0.0.0 

###How container networking work
Containers are bound to a host connection unless two thing are configured to allow such configuration

####IP_Forward
Is the host machine willing to forward IP packets? This is governed by the ip_forward system parameter for more check out this article about [IP forwarding](http://www.ducea.com/2006/08/01/how-to-enable-ip-forwarding-in-linux/)

####IPTables
Iptables is a command-line firewall utility that uses policy chains to allow or block traffic. When a connection tries to establish itself on your system, iptables looks for a rule in its list to match it to. If it doesn’t find one, it resorts to the default action. 

**Types of Chains :**

iptables uses three different chains:

* 
**Input**:

    This chain is used to control the behavior for incoming connections. For example, if a user attempts to SSH into your PC/server, iptables will attempt to match the IP address and port to a rule in the input chain.

* 
**Forward**:

    This chain is used for incoming connections that aren’t actually being delivered locally. Think of a router – data is always being sent to it but rarely actually destined for the router itself; the data is just forwarded to its target. Unless you’re doing some kind of routing, NATing, or something else on your system that requires forwarding, you won’t even use this chain.

* 
**Output**:
    
    This chain is used for outgoing connections. For example, if you try to ping howtogeek.com, iptables will check its output chain to see what the rules are regarding ping and howtogeek.com before making a decision to allow or deny the connection attempt.

###Assigned IP:

There are two ways to find the assigned IP Address for a container

####Ifconfig:
you can find the ip address from the container it self 

```root@153151351# ifconfig```

####inspect
the inspect command shows every configuration about the container

```$ sudo docker inspect --format='{{.NetworkSettings.IPAddress}}' container_name```

    172.17.0.69

This is the assigned IP address to the container and you can even ping it.

###Assign an IP to a continer

###Assign a DNS to a container

###Mac Address
