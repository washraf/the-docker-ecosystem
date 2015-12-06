# Container Control Commands

### Docker Start, Stop and Restart
These three commands are used to change the state of a container from running to stopped or restart it.

**Stop:** When a user issues this command, the Docker engine sends SIGTERM (-15) to the main process, which is running inside the container.

The **SIGTERM** signal requests the process to terminate itself gracefully. Most of the processes would handle this signal and facilitate a graceful exit. However, if this process fails to do so, then the Docker engine will wait for a grace period. Even after the grace period, if the process has not been terminated, then the Docker engine will forcefully terminate the process. The forceful termination is achieved by sending **SIGKILL** (-9).

The **SIGKILL** signal cannot be caught or ignored, and so it will result in an abrupt termination of the process without a proper clean-up.

###**Usage**
```$ docker stop | start| restart [OPTIONS] CONTAINER [CONTAINER...]``` 

    [Options]
    -t, --time=10      Seconds to wait for stop before killing it
    
    [Container]	
    Control the container either by Name or ID

###**Example**
```$ sudo docker start Your_Ubuntu_Container```