# Docker vs Virtual Machines

||Container| Hyper visor |
| -- | -- | -- |
| Redundancy|Only Application Code and Data Edited Files| Computation and Memory redundancy |
|Flexibility|Less Flexible,Only Supported in Linux, Cannot host Windows OS|More Flexible where Linux OS can host windows and vice verse|
|Security|Less Secure, DOS attacks can affect others Containers Container with root privileges could affect other Containers | Full Isolation, Hypervisor is responsible of limiting used resource by VM Cross Gust Access is prohibited|
|Creating Time|	Almost instantaneous | Even Preexisting VMs need OS Load Time
|Performance	|Almost Native|	Less than native due to middle ware|
|Consolidation	|Limited by actual Application Usage	|Limited By OS reserved |
|Memory|Allocation	Memory| Allocated Files	Disk Allocated Files|
