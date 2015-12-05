# Capabilities

###Process Capabilities
Each Linux process has four sets of bitmaps.
By Default each bitmap is 32 bit for 32 different capability.
* 
**Effective** (E):
    
    The effective capability set indicates what capabilities are effective The Process can use now

* 
**Permitted** (P):

    The process can have capabilities set in the permitted set that are not in the effective set. This indicates that the process has temporarily disabled this capability. A process is allowed to set a bit in its effective set only if it is available in the permitted set. The distinction between effective and permitted makes it possible for a process to disable, enable and drop privileges

* 
**Inheritable** (I):

    Indicates what capabilities of the current process should be inherited by the program executed by the current process
* 
**Bset**:

    Determine forbidden capabilities

###File Capabilities
Allows set, the forced set, and the effective set
