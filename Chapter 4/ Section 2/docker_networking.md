# Docker Networking

The Docker engine seamlessly selects and assigns an IP address to a container with no intervention from the user, when it gets launched. Well, you might be puzzled on how Docker selects an IP address for a container, and this puzzle is answered in two parts, which are as follows:

1.	During the installation, Docker creates a virtual interface with the name **docker0** on the Docker host. It also selects a private IP address range, and assigns an address from the selected range to the **docker0** virtual interface. This selected IP address is always outside the range of the Docker host IP address in order to avoid an IP address conflict.

2.	Later, when we spin up a container, the Docker engine selects an unused IP address from the IP address range selected for the **docker0** virtual interface. Then, the engine assigns this IP address to the freshly spun container.