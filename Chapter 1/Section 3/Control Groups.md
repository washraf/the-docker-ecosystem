# Control Groups

It’s a method to put processes into groups by allowing the **Following**:
 	
* 
Resource limitation: groups can be set to not exceed a configured memory limit, which also includes the file system cache.

* 
Prioritization: some groups may get a larger share of CPU utilization or disk I/O throughput.

* 
Accounting: measures how much resources certain systems use, which may be used, for example, for billing purposes.

* 
Control: freezing the groups of processes, their checkpointing and restarting

Each cgroup is represented by a directory in the cgroup file system containing the following files describing that cgroup:
* 

Tasks: list of tasks (by PID) attached to that cgroup. 

* 
Cgroup.procs: list of thread group IDs in the cgroup. 

* 
Notify_on_release flag: run the release agent on exit?
* 
Release_agent: the path to use for release notifications (this file exists in the top cgroup only).

