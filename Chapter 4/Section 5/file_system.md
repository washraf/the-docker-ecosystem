# File System

The container root file system could be accessed using the process id we learned from the previous example.

**Step 1 :** Using the last process id 40085

```# cd /proc/40085/root; ls```

    bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var 
**Step 2 :** adding a file from host

```# touch testfromroot```

**Step 3 :** go to container

```root@1b51c60ecc24:/# ls```

    bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  testfromroot  tmp  usr  var
**Step 4 :** Stop the container and check the file system

```# cd /proc/40085```

    -bash: cd: /proc/40085: No such file or directory
