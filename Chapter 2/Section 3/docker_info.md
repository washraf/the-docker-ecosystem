# Docker Info
This command returns a list of any containers, any images (the building blocks Docker uses to build containers), the execution and storage drivers Docker is using, and its basic configuration.

####**Usage:**

```$ Docker info```

####**Example**

```$ sudo docker info```

    Containers: 0 
    Images: 0
    Storage Driver: devicemapper
    Pool Name: docker-253:0-3022913-pool
    Pool Blocksize: 65.54 kB
    Backing Filesystem: xfs
    Data file: /dev/loop0
    Metadata file: /dev/loop1
    Data Space Used: 1.821 GB
    Data Space Total: 107.4 GB
    Data Space Available: 12.85 GB
    Metadata Space Used: 1.479 MB
    Metadata Space Total: 2.147 GB
    Metadata Space Available: 2.146 GB
    Udev Sync Supported: true
    Deferred Removal Enabled: false
    Data loop file: /var/lib/docker/devicemapper/devicemapper/data
    Metadata loop file: /var/lib/docker/devicemapper/devicemapper/metadata
    Library Version: 1.02.93-RHEL7 (2015-01-28)
    Execution Driver: native-0.2
    Logging Driver: json-file
    Kernel Version: 3.10.0-229.el7.x86_64
    Operating System: CentOS Linux 7 (Core)
    CPUs: 4
    Total Memory: 1.948 GiB
    Name: localhost.localdomain
    ID: Q3D4:BORV:ZTAW:QZ2P:I7DI:4SI3:62AT:5UUA:73NN:CVFC:FDKT:PJR4